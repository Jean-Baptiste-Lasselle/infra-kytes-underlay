
# Relevés des étiquetages sur la machine

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

J'ai pu trouver une communication cisco, indiquant qu' ios version 12.4, avait atteind l'`EOL`

# Installation d'un autre OS dans le switch

À voir si nous trouvons une procédure pour implanter un bootloader, en palpant les broches.

# Tests de réceptiion matériel

## Test 1 : se connecter une première fois au switch

Par défaut, telnet et SSH sont désactivés, ce qui n'est pas surprenant. La seule manière d'entrer dans le système, est d'utiliser le port série du switch. La doc cisco, pour la première connexion console, est présente ici : 
https://www.cisco.com/c/en/us/support/docs/switches/catalyst-6000-series-switches/10600-9.html


Pour se connecter à ce port série, on devra utiliser :

* un câble série avec connecteurs `DB9` (côté switch) et `RS232` (autre extrélmité) ( *com7* ... Le câble bleu dans les impressions écran ci-dessous), branché sur la sortie appelée sortie *console* sur le châssis : 

![câble série de type DB9 DB7](https://github.com/Jean-Baptiste-Lasselle/infra-kytes-underlay/raw/master/switchs/cisco-catalyst-3750-24-poe/images/cables-necessaires-cisco-switch-1-console-port-serie-db7-db9.png)

* un câble convertisseur de `DB9` vers `USB` (le côté USB se branchera sur le poste de travail de l'adminstrateur système impliqué) (Le câble blanc dans les impressions écran ci-dessous), reliant le câble série DB7/DB9 , à la prise usb de mon poste de travail :

![câble convertisseur de série vers USB](https://github.com/Jean-Baptiste-Lasselle/infra-kytes-underlay/raw/master/switchs/cisco-catalyst-3750-24-poe/images/cables-necessaires-cisco-switch-2-usb-to-serial.png)

![câble convertisseur de série vers USB](https://github.com/Jean-Baptiste-Lasselle/infra-kytes-underlay/raw/master/switchs/cisco-catalyst-3750-24-poe/images/cables-necessaires-cisco-switch-3-usb-to-serial.png)

* Sur le poste de travail auquel est relié le switch, on utilisera un logiciel de type Putty, pour établir une connexion de type com, avec le taux `BAUDS` adapté.



## Extrait de la doc cisco: connect to console

>  #### Connect a Terminal to Catalyst 1900/2820, 2900/3500XL, 2940, 2950/2955, 2970, 3550, 3560, and 3750 Series Switches
> 
> Use the supplied rollover cable and the DB-9 adapter to connect a PC to the switch console port. You need to provide an
> RJ-45-to-DB-25 female DTE adapter if you want to connect the switch console port to a terminal. 
> You can order a kit (part number ACS-DSBUASYN=) that contains the adapter from Cisco. The PC or terminal must
> support VT100 terminal emulation. The terminal emulation software—frequently a PC application such as
> Microsoft Windows HyperTerminal or Symantec Procomm Plus—makes possible the communication between the
> switch and your PC or terminal during the setup program.
> 
> Follow these steps to connect the PC or terminal to the switch:
> 
>   Be sure that you have configured your PC or terminal emulation software to communicate with the switch via hardware flow control.

Configure the baud rate and character format of the PC or terminal to match these console port default characteristics:
      * 9600 baud
      * 8 data bits
      * 1 stop bit
      * No parity
With the supplied rollover cable, insert the RJ-45 connector into the console port.
    ![schema cisco switch connexion à la console série](https://github.com/Jean-Baptiste-Lasselle/infra-kytes-underlay/raw/master/schema-connect-to-console-cisco-3750-24ports-poe.gif)
Attach the supplied RJ-45-to-DB-9 female DTE adapter to a PC, or attach an appropriate adapter to the terminal.
Insert the other end of the supplied rollover cable in the attached adapter.
Run the terminal emulation program, if you have a PC or a terminal.

#### Table A-1: Console Port Signaling and Cabling with a DB-9 Adapter

| Console Port (DTE) | RJ-45-to-RJ-45 Rollover Cable | 	RJ-45-to-DB-9 Terminal Adapter | Console Device |
|---|---|---|---|
| Signal | RJ-45 Pin | RJ-45 Pin | DB-9 Pin | Signal |
|---|---|---|---|---|
| RTS1 | 1 | 8 | 8 | CTS2 |
| No connection | 2 | 7 | 6 | DSR |
|---|---|---|---|---|
| No connection | 2 | 7 | 6 | DSR |
| TxD3 | 3 | 6 | 2 | RxD4 |
| GND5 	4 	5 	5 	GND
| GND 	5 	4 	5 	GND
| RxD 	6 	3 	3 	TxD
| No connection 	7 	2 	4 	DTR6
| CTS 	8 	1 	7 	RTS

* 1 RTS = Request To Send
* 2 CTS = Clear To Send
* 3 TxD = Transmit Data
* 4 RxD = Receive Data
* 5 GRD = Ground
* 6 DTR = Data Terminal Ready

#### Connect to a Terminal

Use the thin, flat RJ-45-to-RJ-45 rollover cable and RJ-45-to-DB-25 female DTE adapter to connect the console port to a terminal. Table A-2 lists the pinouts for the console port, the RJ-45-to-RJ-45 rollover cable, and the RJ-45-to-DB-25 female DTE adapter.

Note: The RJ-45-to-DB-25 female DTE adapter does not come with the switch. You can order a kit (part number ACS-DSBUASYN=) that contains this adapter from Cisco.
Table A-2: Console Port Signaling and Cabling with a DB-25 Adapter

Console Port (DTE) 	RJ-45-to-RJ-45 Rollover Cable 	RJ-45-to-DB-25 Terminal Adapter 	Console Device
Signal 	RJ-45 Pin 	RJ-45 Pin 	DB-25 Pin 	Signal
RTS 	1 	8 	5 	CTS
No connection 	2 	7 	6 	DSR
TxD 	3 	6 	3 	RxD
GND 	4 	5 	7 	GND
GND 	5 	4 	7 	GND
RxD 	6 	3 	2 	TxD
No connection 	7 	2 	20 	DTR
CTS 	8 	1 	4 	RTS
 
