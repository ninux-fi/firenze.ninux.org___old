---
layout: post
title: !binary |-
  UG9saWN5IHJvdXRpbmcgcGVyIHVzYXJlIGdsaSBzbWFydCBnYXRld2F5
created: 1400969424
---
Per utilizzare correttamente gli smart gateway e consentire alcune configurazioni particolari è consigliabile usare il <em>policy routing</em>.

Questa è la configurazione standard per Firenze da aggiungere al file <em>/etc/rc.local</em> prima di <em>exit 0</em>:

<code>
    #Rotte per raggiungere le destinazioni locali
    #se ci fosse uno scriptino che le parsasse da ip r sarebbe meglio
    #Aggiungere a mano tutte le route presenti nella tabella main esclusa la default
    ip route add 10.150.x.0/24 dev <INTERFACCIA_LAN e MGMT> table 110
    ip rule add from all lookup 110 pref 3


    #Rotte per Ninux table 111 va aggiunta la regola RtTable nel file di conf di olsr (*)
    ip rule add to 10.0.0.0/8 table 111 pref 4
    ip rule add to 172.16.0.0/12 table 111 pref 4
    ip rule add to 192.168.0.0/16 table 111 pref 4
    ip rule add to 150.217.0.0/16 table 111 pref 4
    ip rule add to 176.62.53.32/28 table 111 pref 4


    #Blackhole vari table 114
    ip route add blackhole 10.0.0.0/8 table 114
    ip route add blackhole 172.16.0.0/12 table 114
    ip route add blackhole 192.168.0.0/16 table 114
    ip rule add from all table 114 pref 5

    #Main
    ip rule add from all table main pref 6

    #Table 224 RTTableTunnel (Smart gateway)
    ip rule add from all table 224 pref 7

    #Table 112 RTTableDefault
    ip rule add from all lookup 112 pref 8
</code>

Nel file di configurazione di olsr vanno aggiunte le direttive:

<code>
    RtTable 111
    RtTableDefault 112
    RtTableTunnel 224
</code>



Per i router di frontiera BGP-OLSRD è necessario usare questo script per il policy routing
<code>
tincd -n ninux-fi
tincd -n bgp-isole
ip route add 10.150.25.0/24 dev br-lan table 110
ip route add 150.217.18.0/24 dev eth1 table 110
ip route add 10.150.0.0/24 dev ninux-fi table 110
ip route add 150.217.0.0/16 via 150.217.18.1 table 110
ip route add 10.150.254.0/24 dev bgp-isole table 110

ip rule add from all lookup 110 pref 3

ip rule add to 10.0.0.0/8 table 111 pref 4
ip rule add to 172.16.0.0/12 table 111 pref 4
ip rule add to 192.168.0.0/16 table 111 pref 4
ip rule add to 176.62.53.32/28 table 111 pref 4

ip rule add from 176.62.53.32/28 table 99 pref 5

ip rule add from all table 114 pref 6

ip ru add iif lo lookup main pref 7

ip rule add from all lookup 112 pref 8

ip route add blackhole 10.0.0.0/8 table 114
ip route add blackhole 172.16.0.0/12 table 114
ip route add blackhole 192.168.0.0/16 table 114

ip tunnel add pubblico mode gre local 10.150.25.1 ttl 255
ip link set pubblico up 

ip route add default via 10.150.254.4 table 99
exit 0
</code>

Articolo originariamente pubblicato su http://nazza.servebeer.com/viewtopic.php?f=7&t=19&sid=aafe40bd557b4e17ab8f65f45fc90f58
