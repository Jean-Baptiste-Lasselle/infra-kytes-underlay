
# Relevés des étiquetage sur la machine

Sur le châssis de la machine, les différents étiquetages indiquent les informations suivantes : 

* Le modèle de la machine "CISCO Catalyst 3750 series PoE-24"
* L'adresse MAC de la machine   : `00:17:5A:83:D6:00`
* alimentation AC : 
  * 100/240 V
  * 5.0 A ~ 2.5 A
  * soit une puissance maximale totale de 1200Watts quand même... 
* ios version : 12.2(25)SEB4
* date de fabrication en thailande : 2006/03/11



## Le modèle du switch

D'après [la doc cisco](https://www.cisco.com/c/en/us/products/collateral/switches/catalyst-3750-series-switches/product_data_sheet0900aecd80371991.html), il semble que le modèle exact soit  le :

`Cisco Catalyst 3750-24PS-24 Ethernet 10/100 ports with IEEE 802.3af and Cisco prestandard PoE and two SFP uplinks`


## L'OS du switch

J4ai pu trouver une communication cisco, indiquant qu' ios version 12.4, avait atteind l'`EOL`

# Installation d'un autre OS dans le switch

À voir si nous trouvons une procédure pour implanter un bootloader, en palpant les broches.

# Tests de réceptiion matériel

## Test 1 : se connecter une première fois au switch

Par défaut, telnet et SSH sont désactivés, ce qui n'est pas surprenant. La seule manière d'entrer dans le système, est d'utiliser le port série du switch.

Pour se connecter à ce port série, on devra utiliser :

* un câble série de type DB9 DB7 ( *com7* ... Le câble bleu dans les impressions écran ci-dessous), branché sur la sortie appelée sortie console sur le châssis
![câble série de type DB9 DB7](https://github.com/Jean-Baptiste-Lasselle/infra-kytes-underlay/raw/master/switchs/cisco-catalyst-3750-24-poe/images/cables-necessaires-cisco-switch-1-console-port-serie-db7-db9.png)
* un câble convertisseur de série vers USB (Le câble blanc dans les impressions écran ci-dessous), reliant le câble série DB7/DB9 , à la prise usb de mon poste de travail
![câble convertisseur de série vers USB]((https://github.com/Jean-Baptiste-Lasselle/infra-kytes-underlay/raw/master/switchs/cisco-catalyst-3750-24-poe/images/cables-necessaires-cisco-switch-2-usb-to-serial.png)
![câble convertisseur de série vers USB]((https://github.com/Jean-Baptiste-Lasselle/infra-kytes-underlay/raw/master/switchs/cisco-catalyst-3750-24-poe/images/cables-necessaires-cisco-switch-3-usb-to-serial.png)

* Sur le poste de travail auquel est relié le switch, on utilisera un logiciel de type Putty, pour établir une connexion de type com, avec le taux `BAUDS` adapté.

 	cables-necessaires-cisco-switch-1-console-port-serie-db7-db9.png 	Add files via upload 	a minute ago
	cables-necessaires-cisco-switch-1-console-port-serie-db7-db9.xcf 	Add files via upload 	a minute ago
	cables-necessaires-cisco-switch-2-usb-to-serial.png 	Add files via upload 	a minute ago
	cables-necessaires-cisco-switch-2-usb-to-serial.xcf 	Add files via upload 	a minute ago
	cables-necessaires-cisco-switch-3-usb-to-serial.png 	Add files via upload 	a minute ago
	cables-necessaires-cisco-switch-3-usb-to-serial.xcf 	Add files via upload 	a minute ago
	images.kytes 	Create images.kytes 	2 minutes ago
 
