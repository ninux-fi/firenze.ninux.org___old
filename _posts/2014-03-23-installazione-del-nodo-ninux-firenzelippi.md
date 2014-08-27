---
layout: post
title: !binary |-
  SW5zdGFsbGF6aW9uZSBkZWwgbm9kbyBOaW51eCBGaXJlbnplOkxpcHBp
created: 1395569193
category: nodi
---
Domenica 7 Marzo 2104 un nuovo nodo si è acceso a Firenze.

Già da tempo avevo svolto dei lavori di preparazione, appena dopo il sopralluogo effettuato con Lorenzo ed Emanuele il Novembre scorso.

Per prima cosa ho installato il palo a partire dal sottotetto fissandolo al muro con delle staffe.

<center><img src="{{ "/images/lippi1.jpg" | prepend: site.baseurl }}" width="50%"></center>

 Il palo che ho scelto è di tipo telescopico a 3 elementi di 2 metri ciascuno; questo consente di lavorare agevolmente installando un elemento alla volta.

<center><img src="{{ "/images/lippi2.jpg" | prepend: site.baseurl }}" width="50%"></center>

Ho fissato con delle staffe il primo elemento al muro, poi il secondo elemento, quello che sostiene i tiranti e finalmente il terzo con le antenne. Si arriva così ad una altezza di 5,5m sopra il livello del tetto senza dover usare scale.

<center><img src="{{ "/images/lippi3.jpg" | prepend: site.baseurl }}" width="50%"></center>

Il server Ninux, un vecchio PC stanco di sudare con Windows, sul quale ora gira agilmente e senza sforzo  olsrd è collocato nel seminterrato.

<center><img src="{{ "/images/lippi4.jpg" | prepend: site.baseurl }}" width="50%"></center>

Durante i mesi successivi, in attesa di un po' di bel tempo  ho passato il cavo Ethernet, Cat5 per interni, "Dal Sottotetto al Seminterrato" (sembra il titolo di un  romanzo di avventura), utilizzando le vie cavi condominiali!!!!!!

Finalmente  finiti  i giorni di pioggia e nebbia, Domenica 7 Marzo ...il sole!!!

<center><img src="{{ "/images/lippi5.jpg" | prepend: site.baseurl }}" width="50%"></center>

Ho quindi subito approfittato dell'occasione e ho installato la scatola stagna accanto al palo nel sottotetto. La scatola contiene uno swicth a 8 porte (configurabili con VLAN), due alimentatori POE e una ciabatta.

<center><img src="{{ "/images/lippi6.jpg" | prepend: site.baseurl }}" width="50%"></center>

Avendo utilizzato  dei morsetti  al posto delle solite spine per le alimentazioni a 230 V, la ciabatta mantiene 2 posti liberi che quindi si possono utilizzare in fase di manutenzione. (Trapano, lampada, PC ...)

Sono passato quindi alla installazione delle antenne : 
<ul>
<li>Nanostation M2 diretta verso Next-Emerson</li>
<li>Nanostation 2 diretta verso FabLab</li>
</ul>

<center><img src="{{ "/images/lippi7.jpg" | prepend: site.baseurl }}" width="50%"></center>

Fissate le antenne al palo  con le fascette di dotazione e avendo cura di mantenere l'angolo relativo già predisposto alla configurazione geografica dei nodi di rifermento, ho abbassato l'elemento intermedio (i tiranti si sono semplicemente afflosciati). Ho installato quindi il palo con le antenne (terzo elemento)  fissandolo con due bulloni da 13.

<center><img src="{{ "/images/lippi8.jpg" | prepend: site.baseurl }}" width="50%"></center>

Ho  individuato la direzione in modo che una antenna collimasse con un nodo di riferimento (Next-Emerson), l'altra si è posizionata automaticamente.

Ho calato poi due cavi cat6 da esterno dentro il palo fino al sottotetto, e ho crimpato i connettori Rj45. (@Leandro : "Non è mica difficile ci vogliono meno di 7 ore") Ho sollevato l'elemento alla sua altezza massima.  Ho finalmente sollevato il secondo elemento del palo,fino a tendere di nuovo i tiranti.

Et Voilà les jeux sont fait!!!

Ho collegato il tutto e sono sceso dunque nel seminterrato dove ho piazzato la presa RJ45 al muro (con rigorosa targhetta di  riconoscimento)  e installato olsrd sul PC in ambiente Debian7.0

<center><img src="{{ "/images/lippi9.jpg" | prepend: site.baseurl }}" width="50%"></center>

Finalmente ho cominciato a sparare dei ping.......  Vedo Tutto  !!, (Antenne, Router Internet).

Aspetto ora  consigli e sostegno, non solo morale, per attivare la  connessione verso il primo "1-hop" e cominciare a sparare HELLO To all the World.


Sono proprio contento.

Che soddisfazione ragazzi !!!!

_Salvatore_
