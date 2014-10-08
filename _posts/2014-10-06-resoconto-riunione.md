---
layout: post
title: Resoconto riunione di Lunedì 6 Ottobre 2014
category: resoconti
layout: post
author: Dade94
---

* **Discussione sulle potenzialità della rete ninux**

	Abbiamo parlato della necessità di sfruttare la rete creando nuovi servizi, cosa che riteniamo importante per la sua crescita.
Salvatore ha proposto di sperimentare servizi o attività che riguardino gli interessi che ciascuno di noi ha in qualsiasi ambito (fotografia, musica, progetti scientifici, radio, straming di film), indipendentemente dal fatto che siano o non siano presenti (o realizzabili) attraverso internet.

* **Avvisi in caso di caduta nodo**

	Abbiamo pensato di dare la possibilità al responsabile di un nodo di essere avvisato tramite una email nel caso in cui il nodo non risulti raggiungibile. Per il momento ci sembra che la cosa migliore sia di aggiungere alla pagina "Gestione Nodi" di Salvatore un campo in cui scegliere tra tre opzioni:

	1. nessun avviso.
	2. avviso sulla mailing list.
	3. avviso al proprio indirizzo email.
<BR>

* **Prova del software Cacti**

	Emanuele ha scaricato e configurato Cacti, uno strumento che ci consentirebbe di creare grafici in tempo reale del traffico passante per le antenne e dell'utilizzo di CPU e memoria dei server o dei router tramite il protocollo SNMP.
Abbiamo dedicato l'ultima parte della serata a capire come configurare questo software per creare un grafico del traffico passante per una antenna qualunque (per fare qualche prova abbiamo scelto fiesole). Alla fine ci siamo convinti che siamo in grado di utilizzare Cacti per ricevere le informazioni dalle nostre antenne via SNMP, però, essendo collegati a Ninux via vpn, non siamo riusciti a creare un grafico di prova.
Pensiamo dunque che sarebbe utile installare Cacti su tank2 o su cenerentola, da usare come strumento per monitorare la rete in maniera più approfondita.
