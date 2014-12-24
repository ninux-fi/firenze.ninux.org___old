---
layout: post
title: Resoconto riunione di lunedì 22 dicembre 2014
category: riunioni, test
author: noccio
---

* **Debug del server VoIp**

Iniziato un timido debug sul nostro centralino voip asterisk che
purtroppo ancora non decolla. Durante un primo periodo di test abbiamo
notato che spesso il demone ASTERISK smette di rispondere alle
richieste di registrazione da parte dei vari client SIP finché non si
esegue un bel 'service asterisk restart'. Nell'ultima riunione abbiamo
notato che se un client si connette in vpn questo problema si
verifica con maggiore frequenza ma non siamo del tutto sicuri che la
vpn sia veramente la causa. Dobbiamo approfondire con un tcpdump e
analizzare, quando si presenta il problema, i pacchetti in arrivo e in
partenza da asterisk. Se ci fosse un esperto di Asterisk che ci legge
in lista potrebbe darci il suo contributo.

* Abbiamo disattivato il WDS su alcune antenne perché le prestazioni
sembrano migliorare.

* Infine abbiamo anche fatto un fantastico brindisi prenatalizio :)
