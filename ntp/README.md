# NTP et infra matérielle

Pour ce qui est de l'infrastructure matérielle, selon [une source bien connue](https://www.pool.ntp.org/en/use.html), lorsque l'accuité des horloges d'un système 
d'information est important pour l'activité opérationnelle d'une organisation, il est recommandé de faire usage d'un 
serveur NTP interne au S.I., avec un serveur NTP matériel dédié, par exemple un MEINBERG (les impressions écrna ci-dessous datent du 11 Octobre 2018) : 

![fiche ebay prix]()
![face 1]()
![face 2t]()
![face 3]()
![face 5]()



# Références

https://www.pool.ntp.org/en/use.html


> Consider if the NTP Pool is appropriate for your use. If business, organization or human life depends on having correct time or can be harmed by it being wrong, you shouldn't "just get it off the internet". The NTP Pool is generally very high quality, but it is a service run by volunteers in their spare time. Please talk to your equipment and service vendors about getting local and reliable service setup for you. See also our terms of service. We recommend time servers from Meinberg, but you can also find time servers from End Run, Spectracom and many others. 

> If you have a static IP address and a reasonable Internet connection (bandwidth is not so important, but it should be stable and not too highly loaded), please consider donating your server to the server pool. It doesn't cost you more than a few hundred bytes per second traffic, but you help this project survive. Please read the joining page for more information.

> If your Internet provider has a timeserver, or if you know of a good timeserver near you, you should use that and not this list - you'll probably get better time and you'll use fewer network resources. If you know only one timeserver near you, you can of course use that and two from pool.ntp.org or so.

> It can rarely happen that you are assigned the same timeserver twice - just restarting the ntp server usually solves this problem. If you use a country zone, please note that it may be because there is only one server known in the project - better use a continental zone in that case. You can browse the zones to see how many servers we have in each zone.

> Be friendly. Many servers are provided by volunteers, and almost all time servers are really file or mail or webservers which just happen to also run ntp. So don't use more than four time servers in your configuration, and don't play tricks with burst or minpoll - all you will gain is extra load on the volunteer time servers.

> Make sure that the time zone configuration of your computer is correct. ntpd itself does not do anything about the time zones, it just uses UTC internally.

> If you are synchronising a network to pool.ntp.org, please set up one of your computers as a time server and synchronize the other computers to that one. (you'll have some reading to do - it's not difficult though. And there's always the comp.protocols.time.ntp newsgroup.)

> At this point, I'd like to thank those donating their time and timeservers to this network.


Serveurs matériels dédiés NTP : 

* http://www.endruntechnologies.com/NTP-Servers/gps-cdma-ntp.htm
* https://www.meinbergglobal.com/english/products/ntp-time-server.htm
* https://spectracom.com/products-services/precision-timing#anchor-2172