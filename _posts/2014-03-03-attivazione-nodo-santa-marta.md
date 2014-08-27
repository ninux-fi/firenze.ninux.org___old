---
layout: post
title: !binary |-
  QXR0aXZhemlvbmUgbm9kbyBzYW50YSBtYXJ0YQ==
created: 1393834846
---
Venerdì 21 febbraio 2014 Gabriel e Lorenzo hanno montato gli apparati per il nuovo nodo SantaMarta

Per prima cosa è stata piazzata la scatola stagna sotto al rack dello CSIAF e l'abbiamo alimentata.

http://photogallery.ninux.org/firenze/Santa-Marta/2014-02-20+20.20.11.jpg
http://photogallery.ninux.org/firenze/Santa-Marta/2014-02-20+20.20.39.jpg
http://photogallery.ninux.org/firenze/Santa-Marta/2014-02-20+20.20.25.jpg
http://photogallery.ninux.org/firenze/Santa-Marta/2014-02-21+16.55.52.jpg

Poi sono stati passati i cavi ethernet da esterni da dentro al castello sopra, in totale 4.

http://photogallery.ninux.org/firenze/Santa-Marta/2014-02-21+16.41.52.jpg

La gran parte del tempo è stata impiegata a crimpare gli 8 connettori sul cavo da esterni.

Mentre venivano crimpati i cavi sono stati effettuati alcuni test scoprendo che Fiesole era ben visibile e si riceveva a -72db il nodo a casa dell'amico di Emanuele, così è stata piazzata subito un antenna direzionata verso Fiesole come backbone verso la rete ninux.

http://photogallery.ninux.org/firenze/Santa-Marta/2014-02-21+16.41.56.jpg

L'access point di Fiesole2 è configurato senza WDS mentre era presente sull'antenna di SantaMarta: di conseguenza il link era unidirezionale (L'access point non interpretava i pacchetti 802.11 con wds, ma viceversa sì). Appena eliminato il WDS è subito arrivata connettività verso il resto della rete.

È stata fissata un'altra antenna verso Sesto Fiorentino (http://photogallery.ninux.org/firenze/Santa-Marta/2014-02-21+16.41.56.jpg), una in direzione Arcetri e un'altra verso MaestroIsacco (http://photogallery.ninux.org/firenze/Santa-Marta/P1040769.JPG).

Successivamente ci siamo accorti che alcune antenne erano raggiungibili e non totalmente a caso, e che non erano raggiungibili dal resto della rete. Esse infatti non pingavano il router di terra (10.150.25.1) e quindi lo script di controllo le faceva riavviare. Trovata la causa del problema nel bridge con managing e wifi, in cui invece di esservi solamente eth0.9, era rimasta anche eth0. Dopo questo passaggio è tutto funzionante.

Martedì 25 febbraio ci sono trovati a Santa Marta con un responsabile dello CSIAF e abbiamo collegato il cavo che arriva al centralino dal sotto-tetto a una porta dello switch e nel pomeriggio ha unito questo switch alla sottorete dove risiede anche l'ip pubblico del Lilik (150.217.19.0/24), così facendo possiamo fare tutto il traffico che vogliamo tra nodo e lilik e il router con openwrt che così ha un ip pubblico (150.217.18.250).

Dopodiché abbiamo chiesto al responsabile locale, se fosse possibile annunciare la subnet di ip pubblici (150.217.0.0/16) dell'università all'interno di ninux: la risposta è stata affermativa perché tutte le restrizioni sulla rete sono per il transito sulla rete GARR e non per la sola rete dell'ateneo Unifi.

Al momento abbiamo quindi tutti i servizi web dell'ateneo fiorentino raggiungibili attraverso la nostra rete. L'unico problema rimane la risoluzione dei nomi. In uno scenario di assenza di connettività internet, i DNS server usuali (google freedns alice) non sarebbero raggiungibili e quindi non potremmo risolvere i domini .unifi.it Potremmo ovviare a questo problema integrando i loro dns nel server dns anycast.

Le fotografie del nodo sono tutte raggiungibili su http://photogallery.ninux.org/firenze/Santa-Marta
