---
author: Dade94
layout: post
---

Il nodo è stato montato sul palo dell'antenna TV sul tetto del palazzo, da cui si ha una buona visuale sulle colline e sui tetti dei palazzi intorno.
Le due antenne sono configurate in bridge e collegate a due porte diverse del router (tp-link) con firmware OpenWrt + Olsrd. Router e alimentatori PoE si trovano in una stanza all'ultimo piano.

<div style="float: right" markdown="1">
![antenne](/images/antenne_masaccio.jpg)
</div>

## Primo sopralluogo

Innanzitutto abbiamo disposto lungo il percorso tra router e antenne una guaina da esterni, senza effettuare, per il momento, curve troppo strette (il percorso è piuttosto breve, circa 2,5m); subito dopo abbiamo fatto scorrere all'interno della guaina la sonda passa-cavi, legandovi all'estremità i 2 cavi ethernet ftp per le 2 antenne. Fortunatemente nel muro era già presente un buco alla base del palo, dove abbiamo fatto passare la guaina contenente i cavi; all'esterno abbiamo fissato tutto con nastro isolante e fascette.
A questo punto abbiamo crimpato i connettori alle estremità dei cavi e montato le antenne.

Le direzioni, come pianificato alle riunioni, sono:

1. Nanostation M5 - Fiesole, lavorivirtuali
100. Nanostation M5 - Bellanzer2, unname

I risultati sono i seguenti:

* Verso fiesole il segnale è abbastanza buono, circa -73 per fiesole1 e poco di più per fiesole2 (credevo meglio, considerando che la visuale è libera; provando a ruotare l'antenna cambia poco)
* L'altra antenna l'ho messa a circa 90° rispetto alla prima, non ho ancora provato ad allinearla bene; comunque riesce a sentire bellanzer2 con circa -85.

Purtroppo al momento manca una presa con la messa a terra nella stanza col router; comunque c'è una scatola di deriazioni lì vicino dove è presente anche la terra, quindi sarà facile ottenerla.

Cose da fare per finire/migliorare il lavoro:

* Aggiungere una presa con la messa a terra.
* Migliorare l'allineamento delle antenne.
* Fissare e raggruppare meglio i cavi all'interno.
