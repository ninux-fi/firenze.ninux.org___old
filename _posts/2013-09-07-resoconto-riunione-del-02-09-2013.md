---
layout: post
title: !binary |-
  UmVzb2NvbnRvIHJpdW5pb25lIGRlbCAwMi8wOS8yMDEz
created: 1378520210
---
anzitutto ieri c'erano diverse persone nuove, che spero nel frattempo si siano iscritti alla lista. Mi scuso se abbiamo avuto poco tempo per socializzare, ma come avete visto avevamo un po' di decisioni da prendere che ci hanno portato via un po' di tempo. Spero che nel frattempo mettiate un nodo potenziale sul mapserver e vi iscriviate in lista.

Abbiamo fatto un po' di ragionamenti sul nodo da mettere all'ARCI. C'è già un cavo, che passa per alcune stanze di cui non abbiamo le chiavi.  Al momento quindi è difficile pensare di mettercene un altro, si deve usare quello. Volendo mettere più apparati, abbiamo deciso per la seguente soluzione:

- si mette un alimentatore PoE a terra su cui far passare 48v, leag dovrebbe avere un alimentatore da prestarci, prima di comprarne uno definitivo.

- Leag si è offerto di fare uno splitter per l'alimentazione, ovvero, il cavo ethernet arriva in una scatola da cui partono un cavo per alimentare uno switch (femmina) e tre cavi per gli apparati (maschi) e il cavo di rete. Ai maschi ci attacchiamo dei PoE injector (alessio ne ha un po') per gli apparati.

- si mette un tplink (di Alessio) sul tetto da cui partono i cavi per gli apparati

- si montano 2 x M5 (che hanno una antonio, una alessio)
     
- si mette un tplink a valle nella stanza degli apparati per fare la distribuzione

- possiamo mettere il mini pc di leandro, trovare una connessione a internet e metterci tinc così facciamo il management da remoto

Tutto questo si fa in due momenti: una sera che ci dirà Leag (probabilmente da lui) per fare il lavoro di saldatura. Un altro momento (che se siamo abbastanza potrebbe essere anche in parallelo, oppure tra due lunedì) per fare la configurazione degli apparati.

Durante il lavoro, tassativamente bisogna scrivere qualche appunto per preparare la presentazione al ninux-day (compreso l'aggeggio saldato).

Per la parte in muratura Michel si offerto di darci piastra e staffe, dobbiamo comprare il palo (~10€ da paoletti). Ricordiamoci di usare il cavo di messa a terra che c'è sul tetto

Per fare la parte sul muro bisogna trovare un giorno con ARCI, in modo da poter anche decidere sulla stanza dove mettere tutto.
