---
layout: post
title: Resoconto della riunione del 15 Febbraio 2016
category: resoconti, riunioni
author: salvatore
---

Abbiamo collaudato il nodo Nomade costituito da una raspberry, uno switch da quattro soldi e un'antenna
M2 o M5 all'occorrenza intercambiabili.<br>
Il tutto è assemblato su carpenteria lignea<br>
Tanto per avere una idea fate riferimento alla immagine qui sotto.<br>

![Minix il nodo Nomade minimo](/images/minix.jpg "Minix il nodo Nomade")

Sulla raspberry è stata installata l'ultima versione lite di raspbian (L'interfaccia grafica non serve)
scaricabile da [https://www.raspberrypi.org/downloads/raspbian/](https://www.raspberrypi.org/downloads/raspbian/)<br>

In ambiente Debian sono stati installati semplicemente con apt-get i seguenti pacchetti :<br>

- olsrd

- vlan

- isc-dhcp-server

Il Nodo Nomade  si presenta sulla rete ninux con l'indirizzo 172.19.150.2  ed esporta la
rete locale 10.150.17.0/24 come registrato già da tempo su ninux.org.

Due sono le reti configurate sulla unica porta ethernet della raspberry:

- eth0 con indirizzo 10.150.17.1 al server olsr per la rete locale

- eth0.3  con indirizzo 172.19.150.2 

Il server dhcp assegna indirizzi ai vari dispositivi collegati tramite lo switch.

[http://wiki.ninux.org/Firenze/GestioneIndirizzi](http://wiki.ninux.org/Firenze/GestioneIndirizzi)

Il collaudo è andato molto bene, abbiamo sostituito la M2 installata con un M5 opportunamente
dislocata fuori , al freddo, in zona di copertura della antenne di Bellanzer2.
Il nodo si è collegato immediatamente alla rete e attraverso di esso abbiamo eseguito tutte le operazioni di 
installazione e di settaggio della rasperry che servirà a costituire il Kit NodoFoglia di cui parleremo dopo.<br>
Minix si presta bene per fare le presentazioni e per fare i sopralluoghi per l'istallazione di nuovi nodi come scanner di campo.
Qualcuno propone di alimentarlo a batteria. Forse sarebbe meglio un gruppettino di continuità visto che la M2/M5 richiede una tensione di
almeno 24 V. Un prossimo sviluppo è quello di dotare Minix di una interfaccia WiFi (Adattatore usb).Ci stiamo lavorando!.<br>
 Si è anche lavorato con le raspberry (con su raspbian) di Leonardo e Emanuele per la  configurazione del  Kit NodoFoglia Minimo.
Come tutti saprete il nodo Kit dovrebbe rappresentare  la base minima di nodo (foglia) realizzabile con una raspberry per fare il routing a terra e una antenna M2/M5 o altro.
In questo modo avremmo modo di offrire a chi volesse installare un nuovo nodo ninux una base da cui partire e con la quale usufruire da subito dei servizi 
offerti dalla rete comunitaria.<br> 
Tutto questo anche in previsione del fatto che  noi di Ninux Firenze ci siamo ripromessi di dare supporto alla  iniziativa del Comitato MammeNoInceneritore
 per  installare stazioni personali di misura del PM10/PM2.5 e soprattutto alla raccolta e  all'accesso dei dati da queste misurati.

Abbiamo installato YunoHost, ambiente grafico Web Based di configurazione e installazione di pacchetti per debian: [https://yunohost.org/#/](https://yunohost.org/#/)<br>
Abbiamo anche visto che è possibile predisporre degli script (PHP): nella documentazione di Yunohost c'è un template, per aggiungere altri pacchetti oltre a quelli previsti inizialmente.<br>
Tenteremo di aggiungere la configurazione di OLSR mediante la quale sarà possibile scegliere alcune opzioni, ad esempio:

- Indirizzo del nodo

- Indirizzo della rete locale

- Idirizzo del gateway locale per internet

- Esportazione di Internet (Si/No)

- ed altri items da definire.


Alcuni di noi hanno rinnovato la tessera ARCI.


