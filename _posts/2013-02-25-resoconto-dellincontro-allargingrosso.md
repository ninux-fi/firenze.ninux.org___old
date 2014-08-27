---
layout: post
title: !binary |-
  UmVzb2NvbnRvIGRlbGwnaW5jb250cm8gYWxsJ2FyZ2luZ3Jvc3Nv
created: 1361815484
---
Il 23 febbraio ci siamo trovati all'<a href="http://www.firenze.ninux.org/node/29">argingrosso</a> per sistemare il nodo e spippolare un po'.

Questo è un resoconto:

Abbiamo rianimato il nodo Argingrosso. Abbiamo riflashato la M2 nuova, l'abbiamo configurata con gli IP giusti e montata sul palo. Abbiamo un altro link sulla mappa!

Bisogna adesso andare al nodo Firenze::Mi e fare un po' di tuning sull'orientamento della M2 per migliorare la potenza ricevuta, poi fare qualche test con l'ampiezza dei canali ed altri parametri.

Non abbiamo fatto in tempo a fare una scansione verso sesto (nodo di leag) che però probabilmente è raggiungibile e verso Fiesole non abbiamo nemmeno provato dato che c'è un palazzo nel mezzo.

Oltre a questo abbiamo ri-lavorato sulla configurazione supernodo in bridge. Abbiamo risolto il problema che l'altra volta aveva prodotto un link asimmetrico (solo un parametro di configurazione sbagliato) e siamo andati avanti. Abbiamo anche deciso però che la configurazione che volevamo fare inzialmente può essere migliorata perché nella pratica bridga tutti i tronconi della rete. Allora, ho ridisegnato la rete che vogliamo fare, nell'immagine che ho messo qui:

http://leonardo.ma/upload-manual/bridged-net.png (anche allegato al presente articolo)

in cui:
<ul>
<li> i link solidi sono wired, quelli tratteggiati sono wireless</li>
<li> i nodi M2 sono antenne stile ubiquiti</li>
<li> quello nel mezzo è uno switch</li>
<li> il tp-link è un nodo di rete qualsiasi</li>
</ul>

La configurazione con cui abbiamo cominciato metteva in bridge i link 1-2-3. Lo scopo è rendere i nodi sul tetto "stupidi" metterli in bridge e far andare OLSR solo sul tp-link. Il vantaggio è che hai un solo nodo da configurare, e meno segnalazione su OLSR, perché hai un solo MPR (il tp-link) invece che uno per ciascuna antenna sul tetto.

Lo svantaggio è che bridgando i link 1 e 2 i nodi tra casa 1 e 3 finiscono per essere nella stessa LAN, ovvero sono vicini ad un-hop. Se da Casa-2 si manda un pacchetto a Casa-1, arriva anche a Casa-3. Ovvero, la rete diventa un unico dominio broadcast, e alla lunga non scala più.

Allora riprendendo l'email di Dario di qualche settimana fa, abbiamo cominciato a lavorare per separare i link 1-3 e 1-2 su due vlan diverse. Questo o si fa con uno switch managed, oppure usando antenne che supportano Vlan diverse. La cosa si complica sul tp-link perché sulla stessa porta ci sono attestate due vlan diverse, quindi bisogna fare un interfaccia virtuale per vlan. A quel punto entrambe devono avere un IP e bisogna configurare OLSR per usarle entrambe.

Abbiamo cominciato ma non siamo arrivati in fondo per motivi di tempo. Alessio ha tutto l'ambaradan, già configurato per ricominciare da li la prossima riunione (ed anche un prezioso foglio di carta con scritto lo schema della rete e tutti gli indirizzi).
