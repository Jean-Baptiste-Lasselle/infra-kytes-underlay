
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

## Test 1 : se connecter en telnet ou SSH au switch

