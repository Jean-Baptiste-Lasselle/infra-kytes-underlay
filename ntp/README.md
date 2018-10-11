# NTP et infra matérielle

## Matériel

### Pourquoi un serveur NTP matériel dédié

Ces serveurs sont conçus pour y brancher un type de *récepteur* (*receiver*).
Ce *récepteur* reçoit un signal d'horodatage, d'une source primaire comme une source gouvernenmentale, et fait ainsi du serveur un serveur NTP de strate 1 à part entière, et complètement privé.

### Quelques exemples de récepteurs

![magnetic-mount CDMA antenna](https://github.com/Jean-Baptiste-Lasselle/infra-kytes-underlay/raw/master/ntp/images/serveurs-NTP-exemple-recepteurs.1.png)

* Une antenne satellite GPS (cf. http://www.endruntechnologies.com/NTP-Servers/gps-cdma-ntp.htm ): 

![Antenne GPS](https://github.com/Jean-Baptiste-Lasselle/infra-kytes-underlay/raw/master/ntp/images/AntennaKitTS.jpg)

> This GPS Antenna Kit is included with each Time Server.  The standard kit has 50 ft (15 m) of antenna cable.

> GPS antenna requires view-of-the-sky with roof or window-mount.  Expensive installation and maintenance costs are often required.


* Une `magnetic-mount CDMA antenna` (cf. http://www.endruntechnologies.com/NTP-Servers/gps-cdma-ntp.htm ) : 



![magnetic-mount CDMA antenna](https://github.com/Jean-Baptiste-Lasselle/infra-kytes-underlay/raw/master/ntp/images/PROD_SonomaCdmaAntenna250.jpg)

> The magnetic-mount CDMA antenna is included with each Time Server.  It has 12 ft (3.6m) of cable.

> CDMA antenna works indoors!  You can simply place the antenna on top of your equipment rack inside your data center.




Pour des environnements en indoor, on choisira donc une `magnetic-mount CDMA antenna`, et dans le cas où on aura acc_ès aux toits, on mettra en place une antenne GPS, qui nous permettra d'avoir beaucoup mieux, pour la géolocalisation, et offrir d'autres services internes, ou aux clients.


* Un récepteur GPS MEINBERG

![Page Ebay](https://github.com/Jean-Baptiste-Lasselle/infra-kytes-underlay/raw/master/ntp/images/exemple-recepteur-GPS-MEINBERG/recepteur-GPS-MEINBERG-exemple.png)

![Page Ebay](https://github.com/Jean-Baptiste-Lasselle/infra-kytes-underlay/raw/master/ntp/images/exemple-recepteur-GPS-MEINBERG/s-l1600.jpg)

![Page Ebay](https://github.com/Jean-Baptiste-Lasselle/infra-kytes-underlay/raw/master/ntp/images/exemple-recepteur-GPS-MEINBERG/s-l1600.2.jpg)
![Page Ebay](https://github.com/Jean-Baptiste-Lasselle/infra-kytes-underlay/raw/master/ntp/images/exemple-recepteur-GPS-MEINBERG/s-l1600.3.jpg)
![Page Ebay](https://github.com/Jean-Baptiste-Lasselle/infra-kytes-underlay/raw/master/ntp/images/exemple-recepteur-GPS-MEINBERG/s-l1600.4.jpg)
![Page Ebay](https://github.com/Jean-Baptiste-Lasselle/infra-kytes-underlay/raw/master/ntp/images/exemple-recepteur-GPS-MEINBERG/s-l1600.5.jpg)
![Page Ebay](https://github.com/Jean-Baptiste-Lasselle/infra-kytes-underlay/raw/master/ntp/images/exemple-recepteur-GPS-MEINBERG/s-l1600.6.jpg)
![Page Ebay](https://github.com/Jean-Baptiste-Lasselle/infra-kytes-underlay/raw/master/ntp/images/exemple-recepteur-GPS-MEINBERG/s-l1600.7.jpg)
![Page Ebay](https://github.com/Jean-Baptiste-Lasselle/infra-kytes-underlay/raw/master/ntp/images/exemple-recepteur-GPS-MEINBERG/s-l1600.8.jpg)
![Page Ebay](https://github.com/Jean-Baptiste-Lasselle/infra-kytes-underlay/raw/master/ntp/images/exemple-recepteur-GPS-MEINBERG/s-l1600.9.jpg)
![Page Ebay](https://github.com/Jean-Baptiste-Lasselle/infra-kytes-underlay/raw/master/ntp/images/exemple-recepteur-GPS-MEINBERG/s-l1600.10.jpg)


### Un exemple de serveur dédié

Voic par exemple un MEINBERG (les impressions écran ci-dessous datent du 11 Octobre 2018) : 

![fiche ebay prix](https://github.com/Jean-Baptiste-Lasselle/infra-kytes-underlay/raw/master/ntp/images/serveurs-NTP-MEINBERG.exemple.ebay.5.png)
![face 1](https://github.com/Jean-Baptiste-Lasselle/infra-kytes-underlay/raw/master/ntp/images/serveurs-NTP-MEINBERG.exemple.ebay.1.png)
![face 2t](https://github.com/Jean-Baptiste-Lasselle/infra-kytes-underlay/raw/master/ntp/images/serveurs-NTP-MEINBERG.exemple.ebay.2.png)
![face 3](https://github.com/Jean-Baptiste-Lasselle/infra-kytes-underlay/raw/master/ntp/images/serveurs-NTP-MEINBERG.exemple.ebay.3.png)
![face 5](https://github.com/Jean-Baptiste-Lasselle/infra-kytes-underlay/raw/master/ntp/images/serveurs-NTP-MEINBERG.exemple.ebay.4.png)

Il faut aussi compter l'achat d'u connecteur faisant du serveur un serveur NTP `stratum 1` . Par exemple :



*Autres Serveurs matériels dédiés NTP*

* http://www.endruntechnologies.com/NTP-Servers/gps-cdma-ntp.htm
* https://www.meinbergglobal.com/english/products/ntp-time-server.htm
* https://spectracom.com/products-services/precision-timing#anchor-2172





## Opérationnel: Quand un matériel NTP dédié est-il nécessaire?

Pour ce qui est de l'infrastructure matérielle, selon [une source bien connue](https://www.pool.ntp.org/en/use.html), lorsque l'accuité des horloges d'un système d'information est important pour l'activité opérationnelle d'une organisation, il est recommandé de faire usage d'un serveur NTP interne au S.I., avec un serveur NTP matériel dédié.

# Références et bonnes pratiques

https://www.pool.ntp.org/en/use.html


> Consider if the NTP Pool is appropriate for your use. If business, organization or human life depends on having correct time or can be harmed by it being wrong, you shouldn't "just get it off the internet". The NTP Pool is generally very high quality, but it is a service run by volunteers in their spare time. Please talk to your equipment and service vendors about getting local and reliable service setup for you. See also our terms of service. We recommend time servers from Meinberg, but you can also find time servers from End Run, Spectracom and many others. 

> If you have a static IP address and a reasonable Internet connection (bandwidth is not so important, but it should be stable and not too highly loaded), please consider donating your server to the server pool. It doesn't cost you more than a few hundred bytes per second traffic, but you help this project survive. Please read the joining page for more information.

> If your Internet provider has a timeserver, or if you know of a good timeserver near you, you should use that and not this list - you'll probably get better time and you'll use fewer network resources. If you know only one timeserver near you, you can of course use that and two from pool.ntp.org or so.

> It can rarely happen that you are assigned the same timeserver twice - just restarting the ntp server usually solves this problem. If you use a country zone, please note that it may be because there is only one server known in the project - better use a continental zone in that case. You can browse the zones to see how many servers we have in each zone.

> Be friendly. Many servers are provided by volunteers, and almost all time servers are really file or mail or webservers which just happen to also run ntp. So don't use more than four time servers in your configuration, and don't play tricks with burst or minpoll - all you will gain is extra load on the volunteer time servers.

> Make sure that the time zone configuration of your computer is correct. ntpd itself does not do anything about the time zones, it just uses UTC internally.

> If you are synchronising a network to pool.ntp.org, please set up one of your computers as a time server and synchronize the other computers to that one. (you'll have some reading to do - it's not difficult though. And there's always the comp.protocols.time.ntp newsgroup.)

> At this point, I'd like to thank those donating their time and timeservers to this network.
