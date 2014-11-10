---
layout: post
title: Resoconto spostamento server domenica 9 novembre 2014
category: resoconti
layout: post
author: noccio
---

Abbiamo spostato il server. Nel dettaglio abbiamo spostato il tp-link
dentro al rack, perché il cavo di alimentazione non era abbastanza lungo
per arrivare al rack, ci abbiamo attaccato sia internet che il cavo che
va al tetto, abbiamo riintestato tutte le porte delle altre stanze allo
switch principale, quindi vanno su internet. Abbiamo segnato il vecchio
cavo wireless, così se ci serve lo ritroviamo facilmente. Il tp-link
arriva anche al bar del piano, se ci facciamo qualche riunione.

Abbiamo anche cercato di capire come si arriva al bar al piano terra.
C'è una porta che arriva al nostro rack e si attacca ad uno switchetto
piccolo, che è quello di firenze-wifi. Le altre porte del bar vanno
all'altro switch a cui non abbiamo accesso (anche se ce n'è una con un
nome che sembra andare al nostro switch ma è morta). Quindi dobbiamo
mettere uno/due switch managed (uno al bar ed uno su) per far arrivare
una vlan nostra giù, oppure provare a farcela arrivare attraverso gli
switch unmanaged, oppure separarli a livello IP in qualche modo, che è
la cosa meglio.

Ci manca da fare:

- portare un cavo di alimentazione femmina-femmina per cenerentola.
L'abbiamo staccato per attaccare lo switch ed al momento cenerentola è
spenta.

- sistemare i cavi che escono dall'armadio di rete e vanno nel nostro
rack con una canalina. Ne servono 4 metri netti

- spostare un altro po di cose che abbiamo lasciato nella vecchia
stanza in una scatola, perché non abbiamo ancora l'armadio nella nuova.

Più in dettaglio delle cose che abbiamo fatto, a futura memoria:

- collegata porta 27 (stanza col cavo wireless) alla 12 dello switch
- nella stanza ex-server collegata porta 3 a 5 dello switch e 2 a 16
dello switch.
