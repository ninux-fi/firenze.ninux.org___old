---
layout: post
title: ffmpeg questo s-conosciuto
category: exfila, stream, youtube
author: emanuele
---

Durante gli  ultimi incontri ci siamo concentrati sulla possibilità di sperimentare lo streaming audio-video sfruttando in parte la rete ninux.

L'idea è stata quella di sfruttare l'occasione della [festa dell'exfila](http://www.firenze.ninux.org/exfila,%20incontri/2015/09/03/Programma-ExSummerFest2015/) degli scorsi 11-12-13 settembre come pretesto per mettere alla prova la rete e streammare qualche evento musicale e così abbiamo iniziato la sperimentazione.

Per ridurre le variabili in gioco abbiamo scelto il canale di youtube come streamer finale verso l'utente, per ovvii motivi, così ci siamo concentrati sul software ffmpeg, per la cattura, l'encoding e la pubblicazione server-client per la trasmissione verso i server di youtube.

La cattura è avvenuta sfruttando una banale web-cam usb rilevata su
*/dev/video0* di un portatile. La riga di comando per catturare dal
dispositivo video e audio e stremmare su un server è simile alla
seguente:

`ffmpeg -f v4l2 -i /dev/video0 -f alsa -ac 2 -i pulse -s 426x240
-vcodec libx264 -pix_fmt yuv420p -vb 1000k -profile:v auto -preset:v
fast -g 60 -r 30 -acodec libmp3lame -ab 128k -f flv
"rtmp://a.rtmp.youtube.com/live2/nome.utente.aaaa-bbbb-cccc-dddd"`

Descrizione di alcuni parametri:

* *-i* = input

* *-ac* = numero di canali audio

* *-s 426x240* = risoluzione del frame. I formati accettati da
  youtube sono: 426x240 854x480 1280x720

* *-vcodec libx264* = video codec suggerito da youtube

* *-pix_fmt yuv420p* = formato del pixel richiesto da youtube

* *-vb* = video bitrate adeguato alla risoluzione scelta.

* *-preset:v fast* = è la qualità con cui viene effettuato
  l'encoding. Migliore è la qualità (slow), maggiore impegno per
  la cpu ma flusso più leggero sulla rete!

* *-g 60* = video gop size. È la quantità di fotogrammi tra un
  keyframe e l'altro. 60 significa un keyframe ogni 2 secondi
  (suggerito da youtube) se imposto il framerate a 30.

* *-r 30* = framerate (richiesto da youtube)

* *-acodec libmp3lame* oppure *aac* è il codec di compressione
  audio richiesto da youtube.

* *-ab 128k* = bitrate audio.

La seconda parte della riga di comando *-f flv
"rtmp://a.rtmp.youtube.com/live2/nome.utente.aaaa-bbbb-cccc-dddd"*
produce l'output verso i server youtube, rispettando i requisiti
severi di quest'ultimo.

Qui sono sorti i primi problemi. La banda in upload da exfila non era
sufficiente così abbiamo pensato di utilizzare un tool di ffmpeg,
*ffserver* che si occupa di pubblicare una sorgente audio-video, dopo
averla encodata nel formato adatto, nella nostra rete ninux.

Questa la rigadi comando per ffserver:

`ffserver -f ffserver.conf`

Questo il file di configurazione:

*[ffserver.conf]*

	HTTPPort 8091

	HTTPBindAddress 0.0.0.0

	MaxHTTPConnections 1000

	MaxClients 10

	MaxBandwidth 333000

	CustomLog -

	<Feed feed1.ffm>

	File /tmp/feed1.ffm

	FileMaxSize 400K

	ACL allow 127.0.0.1

	launch ffmpeg -f v4l2 -i /dev/video0 -f alsa -ac 2 -i pulse 

	</Feed>

	<stream live.flv>

	Format flv

	Feed feed1.ffm

	VideoCodec libx264

	VideoFrameRate 30

	VideoBitRate 800

	VideoSize 426x240 #854x480 #1280x720 #426x240

	VideoGopSize 30

	VideoBufferSize 1000

	AVOptionVideo crf 23

	AVOptionVideo preset fast profile auto

	PixelFormat yuv420p

	AVOptionVideo flags +global_header

	AudioCodec aac

	Strict -2

	AudioBitRate 128

	AudioChannels 2

	AudioSampleRate 44100

	AVOptionAudio flags +global_header

	</Stream>

	<Stream stat.html>

	Format status

	ACL allow localhost

	ACL allow 192.168.0.0 192.168.255.255

	</Stream>

	<Redirect index.html>

	URL http://www.ffmpeg.org/

	</Redirect>

A questo punto è bastato utilizzare un'altra macchina su un nodo
direttamente collegato alla fibra 30/3 con un ffmpeg che richiedeva al
ffserver il flusso e lo "copiava" sui server youtube. Questa è la riga
di comando locale:

	ffmpeg -i http://10.150.22.xxx:8091/live.flv -codec:copy -f flv "rtmp://a.rtmp.youtube.com/live2/nome.utente.aaaa-bbbb-cccc-dddd"

Questa ci è sembrata la soluzione ideale, anche se perfezionabile, per
sfruttare la rete ninux ad alta velocità e uscire da una fibra per
l'upload.

Anche se tecnicamente tutto ha funzionato, i risultati in termini di
qualità non sono stati all'altezza delle aspettative a causa della
rete attualmente non in perfetta efficienza, ma abbiamo già
programmato una serie di test per individuare i nodi deboli da
potenziare.

