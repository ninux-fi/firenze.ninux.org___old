---
layout: post
title: NetPing - Progetto di monitoring e analisi della rete Ninux-Firenze
category: monitoring, rete
author: salvatore
---

Fare streaming delle nostre attività sulla rete Ninux ?

Attivare servizi di archiviazione , sincronizzazione e Data base condivisi?

Ascoltare musica e condividere contenuti ?

Tutto è possibile e a questo stiamo penzsando noi "ninuxari" del gruppo di Firenze.
Per farlo ci vuole cher la comunicazuìione tra i nodi sia affidabile , stabile e veloce.
Ci siamo guardati in faccia e ci siamo chiesti :"Come sta la nostra rete?",
dopo un imbarazzante silenzio abiamo ripsosto : "Non lo so!" 

E' da questa necessità che è venuta l'idea del progetto NetPing: un sistema per verificare la velocità di connessione tra un nodo ed
un altro e di come questa varia nel tempo.
Il sistema si basa sul concetto trasmettere pacchetti (TCP) di lunghezza nota al nodo vicino (1-hop).
La velocità di comunicazione è calcolata in base al tempo necessario a trasmettere i pacchetti e quello di ricevere la risposta.
Lo strumento adeguato a questo scopo è il comando di "ping" mediante il quale si possono trasmettere pacchetti in numero e lunghezza variabile
e la risposta fornita contine già inforamzionei del tempo minimo medio e massimo di trasmissione.
Se i pacchetti sono abbastanza lunghi si può affermare con buona approssimazione che il tempo di trasmissione è proporzionale alla velocità di comunicazione tra i nodi.
ad esempio :  con
 
 #ping -c  10 -s 800 172.19.180.1

  --- 172.19.189.1 ping statistics ---
 10 packets transmitted, 10 received, 0% packet loss, time 32ms
 rtt min/avg/max/mdev = 2.209/3.298/5.260/0.981 ms, ipg/ewma 3.573/3.736 ms

si calcola che la velocità  media di comunicazione con il nodo 172.19.189.1 è di 1600*8/3.298) = 3381 kb/s

Il sistema è così organizzato:

Su ogni nodo sul cui apparato gira OLSR (OpenWrt , Debian ..) viene installato lo script:  
#check_neighs.sh
questo viene attivato ogni ora concron e  aggoirno un file ping.csv che riporta i risultati del ping verso i nodo vicini 1-hop.
E' necessario che il nodo fornisca un servizo HTTP.
Da qualche parte , nella rete, (nel nostro caso : 10.150.28.10) è presente un server che a cadenza di un ora
interroga ogni nodo e scarica il file "ping.csv" attraverso 
#wget :http/ping/indirizzo_del_nodo  
ne esegue la differenza con quello sacricato durante la precedente scansione,
e archivia i dati nel data base (MySql) net_ping.

![Schema di Netping](/images/netping.jpg "Schema di NetPing")

Al momento il sistema è attivo su 7 nodi della rete e sta fornendo i primi risultati.
Contiamo di poter installare lo script entro su tutti i nodi entro la prossima setimana.
Stiamo lavorando ad un sistema di analisi e rappresentazione dei dati Web Based. Un esempio è [qui](ping.cube.l0g.in/links/).

Il progetto è interamente scaricabile da :
[https://github.com/ninux-fi/monitoring_scripts.git](https://github.com/ninux-fi/monitoring_scripts.git)


