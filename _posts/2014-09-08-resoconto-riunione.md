---
layout: post
title: Resoconto riunione di lunedì 8 settembre 2014
category: resoconti
layout: post
author: noccio
---

Ancora una riunione molto frequentata e piena di discorsi e facce nuove.

## Sistemazione dei server nel rack

Dopo una lotta faticosa abbiamo distanziato i due server nel nostro
rack di modo da migliorare la circolazione dell'aria e quindi il
raffreddamento.

Appena entrati nella nostra stanzina abbiamo verificato che il calore
interno era molto minore della nostra precedente visita e che i due
server facevano molto meno rumore, probabilmente perché avevamo
lasciato la finestra aperta e anche perché tank2 non sembrava più
sotto sforzo.

Comunque adesso i due server sono ben distanziati.

## Sistema di monitoraggio centralizzato

Già dalla precedente riunione era stata espressa la necessità di avere
un sistema di monitoraggio del traffico nella nostra rete.

Usare il sistema con vnstat può essere una prima soluzione che però
non può essere usata facilmente sui router con openwrt (perché sembra
che dia problemi alla memoria interna obbligando all'uso di chiavette
usb esterne) e perché necessita di installazione e configurazione di
software su ogni nodo.

C'è la proposta di Salvatore di interrogare i router da un punto
centrale usando il protocollo
[snmp](https://it.wikipedia.org/wiki/SNMP) e salvare i dati su un
database. Questo sistema permette di monitorare non solo il traffico
di rete ma anche il carico di uso della cpu e della memoria nei nodi
interrogati e di salvare questi dati in formati che siano poi
riutilizzabili anche in altre forme e necessita solo dell'attivazione
del protocollo sugli apparati (normalmente presente) che partecipano
al monitoraggio.

## Nodo di Santa Marta che non fa traffico verso i nostri ip pubblici

Sembra che all'interno della rete della facoltà di ingegneria ci sia
un firewall che blocca le connessioni verso i nostri nodi con ip
pubblici (isolando di conseguenza anche il nostro sito dall'esterno di
internet), probabilmente perché abbiamo fatto troppo traffico dovuto
all'attacco al sito web che abbiamo subito nelle settimane passate.

Dobbiamo contattare i responsabili della rete universitaria per sapere
con più precisione quel che sta succedendo e trovare un modo per
ripristinare questo traffico ora che il nostro sito non dovrebbe più
essere attaccabile nei modi precedenti.

## Nuovo sito statico con jekyll

Dopo ampia e accesa discussione è stato deciso di provare a
trasformare il nostro sito da drupal al generatore di pagine statiche
[jekyll](http://jekyllrb.com/) usando come formato di partenza
[markdown](http://daringfireball.net/projects/markdown/) e un sistema
di controllo di versione su [git](http://www.git-scm.com).

Questo dovrebbe permettere di avere un sito meno impegnativo per i
nostri server e più facilmente replicabile. Di contro però
probabilmente sarà richiesto un livello tecnico più specialistico per
la partecipazione alla scrittura di articoli per il nostro sito: per
mitigare questo scoglio si è pensato di fissare una riunione mirata,
probabilmente (da confermare) già la prossima settimana.
