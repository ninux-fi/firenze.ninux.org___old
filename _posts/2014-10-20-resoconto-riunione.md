---
layout: post
title: Resoconto riunione di lunedì 20 ottobre 2014
category: resoconti
layout: post
author: noccio
---

* **Presentazioni Linux Day**

Abbiamo preparato e condiviso le presentazioni per il Linux Day. Ne
abbiamo una in mattina alle murate di Leandro, con annessa presentazione
di Salvatore sulla sua stazione meteo. Una il pomeriggio all exfila che
fa Ema. Se volete, fate girare le presentazioni prima di sabato così vi
diamo qualche feedback.

* **Script di monitoraggio nodi**

Poi abbiamo migliorato il nostro script per verificare chi ha i plugin
txtinfo e jsoninfo attivi. Salvatore dovrebbe avere una lista dei nodi
con i due plugin attivi, in modo che chi non li ha attivati possa
abilitarli. Quando li abbiamo tutti (o quasi) possiamo cominciare a
navigarli periodicamente per vedere se effettivamente si creano dei
loop, come si vede a volte quando si usa mtr.

    rm $2_ok.txt
	rm $2_nok.txt
	IPLIST=`ip r | grep ^172.19.* | awk '{print $1}' |sort |uniq` 
	for ip in $IPLIST
	do wget --tries=1 --timeout=10 -O lista-$ip-`date +"%d-%m_%H:%M:%S"`.txt http://$ip:$1
	if [ $? -eq 0 ]; 
	then echo $ip >>$2_ok.txt;
	else
	echo $ip>>$2_nok.txt;
	fi
	done

Questo script va avviato con la riga di comando

    #path/nome_script.sh porta nome_file

dove la *porta* vale *2006* quando si voglia scaricare le informazioni
del plugin *txtinfo* mentre *9090* per le stesse informazioni in
formato *json*.

Lo script analizza tutti i nodi con indirizzo 172.19.x.x, salva i file
scaricati e crea una lista con tutti gli indirizzi
che hanno risposto *nome_file_ok.txt* oltre ad un'altra lista con gli
indirizzi che non hanno inviato risposta nel file *file_nok.txt*

Questi file .txt verranno cancellati ogni volta che viene lanciato lo
script.


* **Arredamento stanza**

Abbiamo attaccato il poster di Hackit nella nostra stanza.

* **Sistemazione nodo bellanzer2**

Abbiamo deciso che sabato al Linux Day ne approfittiamo per orientare
un'antenna verso Davide, e magari capire come fare a portare una vlan
ninux nel bar al piano terra, così abbiamo l'accesso direttamente da
li.
