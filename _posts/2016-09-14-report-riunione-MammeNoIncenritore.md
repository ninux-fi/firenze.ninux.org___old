---
layout: post
title: Resoconto della riunione con il comitato MammeNoInceneritore
category: resoconti
author: salvatore
---

Il gruppo Ninux Firenze ringrazia il
[comitato MammeNoInceritore](http://www.mammenoinceneritore.org/) per
l'interesse riservatoci vista l'ampia partecipazione all'incontro:
circa 20 persone.

Il primo argomento è stata la comunicazione di aver raggiunto il
traguardo di 14.000€ sui 15.000€ necessari nel progetto di
[crowfounding iniziato su produzioni dal basso](https://www.produzionidalbasso.com/project/che-aria-tira/)
per la realizzazione delle centraline.

La prima riunione a partire dalle 18:30 ha riguardato la proposta di
acquisto di sensori di qualità ma dal costo abbastanza elevato della
Alfasense.

La decisione del comitato è stata di procedere all'acquisto di un
sensore e quindi affiancarlo alla centralina lowcost in prototipo già
funzionte e in fase di test e ad un'altra centralina esistente
certificata, il tutto da completare possibilmente entro il 15 di
Novembre.

La riunione successiva delle 21:00, avvenuta dopo una lauta e
piacevole cena a base di prelibatezze tedesche, ha riguardato invece
gli aspetti tecnici di connessione delle centraline e acquisizione dei
dati.

Qui la partecipazione e il contributo sono stati generali.

In pratica si è deciso quanto segue: le centraline, in generale
multisensore, quindi non solo rilevatori di PM10 e PM2.5, sono basate
su piattaforme hardware open di varia natura (Arduino, Raspberry,
EPS826) oppure su hardware proprietario. In questo ultimo caso ci si
riferisce a centraline presenti sul mercato "ready to go" e di valore
più alto.

Per quanto riguarda la qualità delle misurazioni si dovrà valutare più
avanti.

Comunque in ogni caso l'hardware dovrebbe preferibilmente consentire
una connessione WiFi con il router nelle abitazioni e con un router
Ninux dove non c'è connessione ad internet.

Sono prevedibili anche situazioni, da analizzare caso per caso,  di
collegamenti cablati.

Per le piattaforme hardware che non presentano la possibilità di
connessione Ethernet deve essere previsto un interfacciamento (RS232,
USB o altro) con Raspberry che realizza il collegamento al router.

Ogni centralina acquisisce dati ogni secondo per un minuto e rimane in
standby per 4 minuti.

Ogni cinque minuti vengono quindi inviati 60 valori per ogni sensore
connesso. C'è da valutare anche l'alternativa di inviare un solo
valore medio basato sul minuto ogni 5 minuti per ogni sensore.

Il protocollo di comunicazione con il server di acquisizione dei dati
sarà basato su HTTP (MQTT?).

I database eventuali individuati per la raccolta dati sono CRATE.IO e
INFLUXDB (scartato con sdegno MySQL) ambedue ottimizzati per acquisire
dati seriali (su base temporale) e che offrono tools di
rappresentazione grafica dei dati.

Inizialmente il server che ospita il database sarà collocato presso il
nodo ninux Firenze::Lippi in quanto è il più direttamente affacciato
sulla piana di Sesto Fiorentino, ha una buona connessione ad internet
ed ha accessibilità per qualunque tipo di manutenzione.

Dovrà essere studiata anche una procedura di identificazione e
validazione della centralina che trasmette i dati facendo riferimento
a soluzioni già adottate in casi analoghi (in pratica probabilmente un
utente e una password).

Verrà inoltre predisposto un repository su github per il software già
sviluppato e da sviluppare in futuro.

I database individuati saranno installati in ambiente Docker in modo
da poterli trasferire con facilità anche su altre macchine.

Saranno effettuati dei test con le due centraline prototipo, basate
sul sensore PM10 e PM2,5 SDS011, costruite da Marco per il comitato
MammeNoInceneritore da Ninux.

È previsto un nuovo incontro operativo per eseguire i primi test di
archiviazione e confrontare i valori delle due centraline.
