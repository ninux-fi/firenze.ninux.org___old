---
published: true
author: Salvatore
layout: post
title: Resoconto della Riunione di Lunedì 1 Settembre 2014
---

Riunione molto partecipata e sentita quella di ieri sera:


1. **Nodo UomoRotabile**:
 Alberto sta tentando di Scovare un "passaggio a Nord-Ovest" attraverso il tetto di un suo amico in Via Reginaldo Giuliani
per poi collegarsi a Firenze:Lippi: Il collegamento si effettuerà a 2,4 GHz.


1. **Nuovo sito**:
Anche se qualcuno storce un pò il naso sembra che jekyll sia la strada che garantisce
una più facile mantenibilità e aggiornamento del sito vista la semplicità della sintassi 
dello strumento.  I presenti erano tutti d'accordo. Bisogna imparare ad usarlo (Parlo per ,me !)


1. **Server Tank2**:
E' stata estratta la macchina dalle guide, non vi dico le difficoltà e i "commenti",
per smontare le ventole e soffiarle con aria secca.
Tutto è stato rimontato e sembra che faccia un pò meno rumore.
Si è poi notato che i due server Cenerentola e Tank2 sono troppo vicini e si facevano caldo l'un con l'altro,
quindi è stato giudicato più "morale" spostare Cenerentola un pò più in alto.
Salvatore porterà le brucole torks per smontare le guide e rimonatarle in posizone più elevata : speriamo che non ci voglia un altro anno come la volta precedente !


1. **Rete Ninux**:
Serve un sistema di monitoraggio della rete, buona la proposta di Leandro con l'uso di VnStat.
Strumento leggero e abbastanza gestibile ma richiede qualche installazione in ogni nodo, comunque consente una analisi del nodo molto dettagliata.
Salvatore ha proposto anche un sistema basato su [SNMP](http://it.wikipedia.org/wiki/Simple_Network_Management_Protocol) per raccogliere dati essenziali dalle antenne Ubiquity,
che hanno il servizio già installato, e archiviarli su un server MySql  in forma tabellare.
Il server poi potrebbe esser replicato anche su un altra macchina e quindi garantire  l'accessibilità.
La base dati costituisce quindi la fonte di accesso per qualunque applicazione web based.

_Salvatore_
