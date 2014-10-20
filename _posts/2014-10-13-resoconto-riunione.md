---
layout: post
title: Resoconto riunione di lunedì 13 ottobre 2014
category: resoconti
layout: post
author: noccio
---

* **Sistemato il router della sala server**

Nella stanza dove abbiamo i nostri due server abbiamo un TP-Link 841
che usiamo come router per le varie parti della nostra rete. Abbiamo
identificato i vari cavi di rete con delle etichette perché siano più
facilmente riconoscibili.

* **Connessione al bar**

Per poter avere connessione con la nostra rete anche dal bar dove
teniamo normalmente le nostre riunioni abbiamo crimpato un nuovo cavo
wireless così da poter portare una M2 nel cortile passando dalla
finestra sopra lo spazio aperto dell'asilo.

La soluzione non è delle più eleganti perché è necessario stendere il
cavo all'inizio della riunione e toglierlo al termine ed inoltre
abbiamo avuto delle difficoltà perché uno dei nostri portatili non
riusciva a connettersi probabilmente per qualche sovrapposizione con
le reti già presenti (in particolare con Firenze-WiFi); questa
soluzione ci ha permesso in compenso di usare la nostra rete
direttamente per tutta la riunione e quindi di cominciare anche a fare
un po' di debugging.

Il cavo è stato ritirato al termine della riunione e riposto nella
nostra stanza insieme all'M2 che è stata contrassegnata con l'adesivo
di Ninux.

* **Debugging della rete**

Da qualche giorno i nodi LavoriVirtuali e RossiniMusicaDalleOnde
lamentano la non raggiungibilità della rete interna.

Inoltre usando la rete abbiamo verificato perdite di connessioni
continue.

Usando mtr per cercare il problema abbiamo trovato dei probabili loop.

Quindi abbiamo messo su uno script per scaricare con txtplugin le rotte
da tutti i nodi che le pubblicano e poi faremo uno script per navigare le
routing table e vedere se ci sono dei loop e chi li crea.

Lo script è il seguente:

    IPLIST=`ip r | grep ^172.19.* | awk '{print $1}' | grep -v '.0$'`
    for ip in $IPLIST
    do wget -O lista-$ip-`date +"%d-%m_%H:%M:%S"`.txt http://$ip:2006
    done

È stato fatto girare da RossiniMusicaDalleOnde per tutta la notte
successiva e i risultati possono essere scaricati da
[questo indirizzo](https://bbs.cybervalley.org/Ninux/CheckOlsr/)
oppure [da rete Ninux](https://10.150.29.2/Ninux/CheckOlsr/)
