---
layout: post
title: Istruzioni per usare peerstreamer nella rete Ninux
category: software, servizi
author: leonardo
---

Queste sono le istruzioni per collegarsi al server peerstreamer in
funzione sul computer cenerentola della nostra rete (10.150.22.100).

- installare peerstreamer, in una versione che permette di separare la
  parte che fa la gestione dei pacchetti dal playout video. Potete
  scaricare
  [qui la versione 32 bit](https://ans.disi.unitn.it:8000/d/5b64fa93b5/)
  e [qui quella 64](https://ans.disi.unitn.it:8000/d/f51bb19fec/)

-  nella cartella trovate un file notes in cui ci sono 4 comandi, i
   primi due non vi interessano perché servono per fare il setup di una
   sorgente il secondo è

   <pre><code>./streamer-udp-grapes-static -i 10.196.37.173 -p 6000 -F null,dechunkiser=rtp,video=7004,audio=7006</code></pre>

Questo fa partire il software che si va a cercare il video.

Per farlo connettere a cenerentola è necessario modificarlo mettendoci
l'ip giusto, 10.150.22.100.

Quando parte si prende un socket su un'interfaccia a caso, quindi se
avete più ip sulla stessa macchina usate *-I nome_interfaccia*. Se
funziona dovrebbe dirvi *First chunk id played out: XXXX* con un
numero.

A questo punto, sulla vostra porta 7004 si apre un socket rtp che
spara il flusso video al quale potete collegarvi usando vlc:

    vlc rtp://@127.0.0.1:7004

Nel caso non dovesse funzionare si può provare a:

- dare i permessi +x ai binari;

- quando peerstreamer parte indica il network-id, che deve essere
  routabile su ninx;

- se sembra funzionare tutto ma vedete solo uno schermo nero,
  considerate che è notte :-)

La cosa interessante è che è peer-to-peer: ovvero se baldarn lo mette
su, ed io lo metto su, il flusso prima viene mandato a baldarn, e poi
baldarn lo rimanda a me, non apriamo due flussi diversi sulla stessa
sorgente, che ovviamente non può scalare.
