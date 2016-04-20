---
layout: post
title: Streaming del concerto da exfila
category: rete, servizi, streaming
author: gabriel
---

Venerdì 11 dicembre 2015 abbiamo provato a fare lo streaming di un
concerto che si stava tenendo nell'auditorium di exfila.

Per prima cosa abbiamo scollegato l'M2 del piano terra e collegato il
cavo alla porta 1p33 presente nell'auditorium.

Abbiamo connesso un portatile alla suddetta porta e collegato l'uscita
del mixer alla scheda audio (maudio mobile pre).

Per provare avevamo 2 server Icecast2, uno nel nodo lavorivirtuali
e l'altro nel nodo Firenze:Tacca. Entrambi i nodi erano distanti vari
hop da exfila.

La configurazione per icecast è quella di default, a parte il binding
che va impostato su 0.0.0.0

Per fare lo streaming dal portatile abbiamo usato darkice, un utility
da linea di comando.

Siamo riusciti a streamare perfettamente a 192bit - 48 khz per qualche
minuto ma sistematicamente dopo qualche minuto cadeva la connessione.

Il problema pare fosse causato da OLSR su tank, il server nel rack.
Dopo qualche minuto infatti il router iniziava ad inviare pacchetti
attraverso la VPN, i pacchetti looppavano e di conseguenza ricevevamo
*ttl expired*.

Quando abbiamo disattivato tinc è andato stabilmente, e quando l'abbiamo
riattivato ha riniziato a flappare.

Inoltre c'era un numero anormale di pacchetti persi tra il portatile e
il router sul tetto.
