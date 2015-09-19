---
layout: post
title: Upgrade del nodo Santa Marta
category: nodi, smarta
author: gabriel
---

Oggi è stato effettuato l'upgrade del nodo Santa Marta.

È stato rimosso il router WDR3500 e i 4 alimentatori POE, per
sostituirli con gli apparati comprati con l'iniziativa dell'anno
scorso.

Le antenne adesso vengono alimentate da uno switch POE: Toughswitch
POE. Il nuovo router, collegato allo switch, è un Edgerouter LITE. Usa
Debian come SO e ha 51MB di ram, quindi è possibile smanettarci
abbastanza.

È configurato solo per ipv4 e usa il Policy Routing perché il nodo ha
anche una connessione ad internet attraverso la rete locale
dell'università che però non possiamo usare.

Come soluzione temporanea le regole di Policy Routing e l'avvio di
olsrd sono in */etc/rc.local*.

![Fotografia della scatola senza il router](/images/SantaMarta-01_2015-09-14.jpg "Fotografia della scatola senza il router")

![Fotografia (molto sfocata) della scatola con il router](/images/SantaMarta-02_2015-09-14.jpg "Fotografia (molto sfocata) della scatola con il router")

Dall'iniziativa avanzano ancora:

- 2 NanoBeam 5ghz

- 4 Nanostation 5ghz

- 1 Picostation 2,4ghz

che potremmo usare per un nuovo nodo presso la sede universitaria di
Sesto Fiorentino.
