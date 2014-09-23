---
title: Nuovo nodo masaccio
author: Dade94
layout: post
---

Il nodo è stato montato sul palo dell'antenna TV sul tetto di un palazzo di via Masaccio ([vedi sul MapServer](http://map.ninux.org/select/firenzemasaccio1/)), da cui si ha una buona visibilità sulle colline e sui tetti dei palazzi intorno.

Questo nodo non ha, per il momento, la funzione di collegare direttamente nuovi membri alla rete; ho deciso di installarlo innanzitutto perchè mia nonna, che abita all'ultimo piano, mi ha dato la possibilità di farlo. Inoltre credo sia una buon posto per installare un piccolo server (se e quando sarò in grado di gestirlo). Infine dovrebbe dare una possibilità in più ad eventuali nuovi ninuxari della zona di collegarsi alla rete.


Il nodo è composto da 2 Nanostation M5 e un router tp-link con OpenWrt, configurati (prima del sopralluogo) seguendo la guida sul routing a terra. Router e alimentatori sono stati posizionati in una stanza all'ultimo piano, molto vicina al palo dell'antenna.


## Primo sopralluogo

Dato che mia nonna non era entusiasta all'idea che mi recassi sul tetto per montare le antenne, ho/ha chiesto l'aiuto di un amico di famiglia (Ismett) che, essendo muratore, ha sicuramente più esperienza di me.

<div style="float: right" markdown="1">
![antenne](/images/antenne_masaccio.jpg)
</div>

Innanzitutto abbiamo disposto lungo il percorso tra router e antenne una guaina da esterni, senza effettuare, per il momento, curve troppo strette (il percorso è piuttosto breve, circa 2,5m); subito dopo abbiamo fatto scorrere all’interno della guaina la sonda passa-cavi, legandovi all’estremità i 2 cavi ethernet ftp per le 2 antenne. Fortunatemente nel muro era già presente un buco alla base del palo, dove abbiamo fatto passare la guaina contenente i cavi; all’esterno abbiamo fissato tutto con nastro isolante e fascette. A questo punto abbiamo crimpato i connettori alle estremità dei cavi e montato le antenne.

Le direzioni, come pianificato alle riunioni, sono:

1. Nanostation M5 - fiesole, lavorivirtuali
1. Nanostation M5 - bellanzer2, unname

I risultati sono i seguenti:

* Verso fiesole il segnale è abbastanza buono, circa -73 per fiesole1 e poco di più per fiesole2 (credevo meglio, considerando che la visuale è libera; provando a ruotare l'antenna cambia poco)
* L'altra antenna è stata messa a circa 90° rispetto alla prima, non ho ancora provato ad allinearla bene; comunque riesce a sentire bellanzer2 con circa -85.

L'unico problema è che al momento manca una presa con la messa a terra nella stanza col router; comunque c'è una scatola di derivazione lì vicino dove è presente anche la terra, quindi sarà facile ottenerla.

Cose da fare per finire/migliorare il lavoro:

* Aggiungere una presa con la messa a terra.
* Migliorare l'allineamento delle antenne.
* Fissare e raggruppare meglio i cavi all'interno.
