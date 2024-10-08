[presentatie](https://learning.ap.be/pluginfile.php/1957746/mod_resource/content/4/01%20-%20Theorie%20-%20Conceptueel%20overzicht%20van%20netwerken%20.pdf)

# Wat is een medium? (meervoud: media)
- In de datacommunicatie: het <span style="color:#c8ab83;">medium</span> datgene waarover signalen worden verstuurd.
- Bedrade voorbeelden:
	- Twisted pair (TP) koperbekabeling
		- <span style="color:#c8ab83;">UTP</span>: unshielded
		- <span style="color:#c8ab83;">STP</span>: shielded
		- <span style="color:#c8ab83;">FTP</span>: foiled
	- <span style="color:#c8ab83;">Coax</span> koperbekabeling
	- Glasvezel (<span style="color:#c8ab83;">fiber</span>)
- Draadloze voorbeelden:
	- Radiostraling
	- Microgolfstraling (wifi, GSM, 4G, ...)
	- Laser
	- Infrarood

# Het internet als voorbeeld
- Miljoenen toestellen die <span style="color:#c8ab83;">verbonden</span> zijn met elkaar
- Toestellen die 1 of meerdere specifieke taken uitvoeren
	- Ofwel <span style="color:#c8ab83;">end systems</span> (=<span style="color:#c8ab83;">hosts</span>)
	- Ofwel <span style="color:#c8ab83;">connectivity devices</span> (toestellen om andere toestellen aan elkaar te koppelen)
+
- Applicaties
+
- Doorgestuurde gegevens (<span style="color:#c8ab83;">data</span>)
+
- Verbindingen (<span style="color:#c8ab83;">links</span>)
	- Bestaande uit verschillende media
	- Elk met eigen beperkingen

- Internet is een aaneenschakeling van verschillende netwerken
	- <span style="color:#c8ab83;">Hiërarchische opbouw</span> -> verschillende <span style="color:#c8ab83;">tiers</span> (gelaagde structuur)
![[Pasted image 20240708150416.png]]

- Communicatie
	- Zenden en ontvangen van boodschappen
	- Moet gebeuren volgens bepaalde afspraken = <span style="color:#c8ab83;">protocollen</span>
- Afspraken / Protocollen worden vastgelegd in documenten = <span style="color:#c8ab83;">standaarden</span>
	- Verschillende organisaties beheren deze documenten
	- vb. RFC, IETF, IEEE, ...
- Internet: een netwerk van netwerken (zie eerder)
	- Wie is eigenaar van toestellen?
	- Wie is eigenaar van data?
	- Wie beheert wat?
	- Wie heeft er zeggenschap?

# Taak van een netwerk?
- Hardware infrastructuur bieden voor zichtbare toepassingen (applicaties)
	- voorbeelden van zichtbare applicaties?
	- Indien via een netwerk ter beschikking gesteld: <span style="color:#c8ab83;">gedistribueerde applicaties</span>
- Er gebeuren op een netwerk ook 'onzichtbare' taken
	- Toepassingen achter de schermen
	- <span style="color:#c8ab83;">Services / Diensten</span>
	- Ofwel <span style="color:#c8ab83;">reliable</span> of <span style="color:#c8ab83;">unreliable</span> (best effort) dienstverlening
	- 'Huishoudelijke' taken zoals <span style="color:#c8ab83;">monitoring</span> en <span style="color:#c8ab83;">rapportering</span>

# Protocollen
- <span style="color:#c8ab83;">Gemaakte afspraken</span> om een goede communicatie te verkrijgen
- Kan zijn op vlak van:
	- Uit te voeren acties voor er gestart wordt met zenden / ontvangen van data
	- Formattering van boodschappen
	- Volgorde van versturen en ontvangen
	- Eisen waaraan de plaatsing van bekabeling en apparaten aan moet voldoen
	- Acties die moeten ondernomen worden als reactie op ontvangen boodschappen
	- ...

# Netwerken vanuit verschillende standpunten
- <span style="color:#c8ab83;">Network edge</span> = applicaties en hosts die zich lokaal bij jouw bevinden
- <span style="color:#c8ab83;">Access network</span> = fysieke infrastructuur die toegang geeft tot andere netwerken
- <span style="color:#c8ab83;">Backbone</span> of <span style="color:#c8ab83;">Network core</span> = onderling verbonden routers / gateways

-> Terminologie vatbaar voor interpretatie afhankelijk van je eigen standpunt / betrokkenheid

# Netwerken volgens schaalgrootte
#LAN #MAN #WAN

## LAN
- <span style="color:#ffb1af;">LAN</span> = Local Area Network
	- kleinschaling
	- korte afstanden
	- eigendom van individu of kleine organisatie (vb. KMO, school of thuis)
	- Beheer bij individu of klein team
## MAN
- <span style="color:#b4f0a8;">MAN</span> = Metropolitan Area Network
	- schaalgrootte  ~ een metropool (een grote stad)
	- afstanden die oplopen tot tientallen kilometers
	- eigendom (meestal) van 1 organisatie
	- groot, verspreid team nodig om te beheren
## WAN
- <span style="color:#cc99fe;">WAN</span> = Wide Area Network
	- schaalgrootte onbeperkt (heel de Aarde + Maan + satellieten + ???)
	- Vele eigenaars en beheerdersteams moeten samenwerken

# Netwerken volgens Topologie
## Ster netwerk
![[Pasted image 20240708151608.png]]
- Hosts verbonden met een hub
- Elke host ontvangt elk signaal op het netwerk

## Bus netwerk
![[Pasted image 20240708151637.png]]
- Hosts verbonden aan gemeenschappelijk medium

## Boom netwerk
![[Pasted image 20240708151655.png]]
- Steeds 1 Route tussen twee nodes

## Ring netwerk
![[Pasted image 20240708151714.png]]
- Geen begin- of eindpunt
- Dubbele ring voor redundantie

## Maas netwerk
![[Pasted image 20240708151737.png]]
- Willekeurig aantal verbindingen tussen nodes
- Onduidelijke structuur
- Full mesh wanneer alle nodes verbindingen hebben naar alle andere nodes

# Technieken en protocollen per type netwerk
- Technieken en protocollen verschillen per type netwerk!
	- <span style="color:#ffb1af;">LAN</span> gebruikt andere protocollen dan <span style="color:#cc99fe;">WAN</span>
	- Busnetwerk gebruikt andere protocollen dan ringnetwerk
	- <span style="color:#ffb1af;">LAN</span> kan opgebouwd worden als bustopologie, maar ook als ringtopologie
	- <span style="color:#cc99fe;">WAN</span> kan opgebouwd worden als een ring- , maar ook als boom- of maastopologie
	- ENZ...
- Technieken en protocollen verschillen ook afhankelijk van het gebruikte medium!
	- Licht kan je niet over een koperkabel transporteren, elektriciteit niet over een glasvezelkabel
- **Gevolg**: Veel verschillende protocollen en technieken om een netwerkinfrastructuur op te bouwen
	- De opleiding behandelt enkel de meeste voorkomende

# De network edge
- Bevat het <span style="color:#c8ab83;">CPE</span> materiaal (Customer Premises Equipment)
- Bevat eind-nodes (<span style="color:#c8ab83;">end-systems</span>)
	- Zullen meestal gebruikt worden om applications op te gebruiken door menselijke gebruikers (vb. web browings, email, ...)
	- Deze hosts werken ofwel volgens
![[Pasted image 20240708152238.png]]

# Acces networks
- Verbinding van edge netwerk aan de backbone
	- Kan residentieel, institutioneel of mobiel netwerk zijn
	- kan <span style="color:#c8ab83;">shared</span> of <span style="color:#c8ab83;">dedicated</span> zijn
	- bevat andere componenten / componenten met andere capaciteiten dan het edge netwerk (vb. modem, andere snelheids-eisen, andere <span style="color:#c8ab83;">throughput</span> vereisten)
- Voorbeelden:
	- <span style="color:#c8ab83;">Dialup</span> via modem (héél vroeger, via klassiek telefonie netwerk, 56 kbps)
	- <span style="color:#c8ab83;">xDSL</span> (digital subscriber line, twisted pai Cu, symmetrisch of asymmetrisch, ~mbps)
	- <span style="color:#c8ab83;">HFC</span> (Hybrid fiber coax, breedband internet + digitale TV + telefonie, asymmetrisch)

- De meest draadloze netwerken kan men ook beschouwen als access network
- Wireless [[01 Introductie en Overview Netwerkopbouw#LAN|LAN]] technologieën
	- Privaat gebruik, om van eender waar in huis / school / bedrijf te koppelen aan het lokale netwerk
	- <span style="color:#c8ab83;">IEEE 802.11 standaarden</span>
- Wireless [[01 Introductie en Overview Netwerkopbouw#WAN|WAN]] technologieën
	- Voorzien door telecom operatoren om te koppelen aan het netwerk van de operator
	- <span style="color:#c8ab83;">3G, 4G, 5G</span>

# De backbone
- Netwerk van verbonden routers, netwerk dat netwerken verbindt, netwerk achter het access netwerk
- Wat is op dit schema edge, access en backbone?
![[Pasted image 20240708152952.png]]


# Manier van data overdracht
## Circuit switching
- Er wordt voor de communicatie een verbinding gelegd tussen zender en ontvanger
- Verschillende verbinding op 1 medium mogelijk
- Elke verbinding krijgt gereserveerde deel van de beschikbare <span style="color:#c8ab83;">bandbreedte</span>
- Dedicated verbinding die <span style="color:#c8ab83;">idle</span> kan staat (verkwisting van capaciteit)
- Continue stroom data over verbinding
- Gegarandeerde <span style="color:#c8ab83;">performantie</span>
- vb. telefonienetwerk

## Packet switching
- Datastroom wordt in kleinere blokken verdeeld (<span style="color:#c8ab83;">packets</span>)
- Packets van verschillende zenders delen het medium en gebruiken de volledige bandbreedte
- Geen garantie over de performantie
- Resource gebruikt 'as-needed'
- Zenders moeten wedijveren voor het gebruik van het medium (= <span style="color:#c8ab83;">contention</span>)
- Medium kan overvol geraken (= <span style="color:#c8ab83;">congestion</span>) met vertraging en verlies van data tot gevolg

# Circuit switching of package switching
- Veronderstel
	- Een lijn met capaciteit van 1Mbps
	- Hiervan moeten verschillende gebruikers kunnen gebruik maken
	- Elke gebruiker verbruikt 100 Kbps als hij actief is
	- Een gebruiker is slecht 10% van de tijd actief
- Bij Circuit switching: 10 gebruikers mogelijk op het netwerk. Idle time hoort toe aan user
- Bij Packet switching: meer dan 10 gebruikers mogelijk op netwerk omdat idle time van 1 gebruiker kan gebruikt worden voor andere gebruiker

- Circuit switching
	- Geeft <span style="color:#c8ab83;">garanties</span> over performantie en beschikbaarheid

- Packet switching:
	- Goed voor <span style="color:#c8ab83;">bursty</span> data
	- <span style="color:#c8ab83;">eenvoudiger</span> dan circuit switching
	- <span style="color:#c8ab83;">Goedkoper</span> dan circuit switching
	- Kans op netwerk <span style="color:#c8ab83;">congestion</span> met impact voor iedereen die het netwerk deelt
	- Soms <span style="color:#c8ab83;">circuit-like gedrag</span> gewenst op een packet switched netwerk (om vb. te voldoen aan maximale vertragingseisen)
		- <span style="color:#c8ab83;">Virtual circuit switching</span> mechanismen

# Soorten communicatie
- Afhankelijk van hoe er gecommuniceerd wordt, onderscheiden we:
	- <span style="color:#ffb1af;">Simplex</span>: enkelrichtingsverkeer. De betrokken partijen hebben een duidelijke rol: ofwel zijn ze zender, ofwel ontvanger. De rollen wisselen niet.
	- <span style="color:#ffdfbe;">Half duplex</span>: strikt geregeld tweerichtingsverkeer. De betrokken partijen kunnen zowel zender als ontvanger zijn en dit kan ook wisselen. Tegelijk zender en ontvanger zijn kan echter niet
	- <span style="color:#ffffbf;">Full duplex</span>: volledig vrij tweerichtingsverkeer. De betrokken partijen kunnen zender en ontvanger tegelijkertijd zijn
- Afhankelijk van het aantal betrokken partijen in de communicatie, onderscheiden we:
	- <span style="color:#ffb1af;">Unicast</span>: 1 node communiceert met exact 1 andere node
	- <span style="color:#ffdfbe;">Multicast</span>: 1 node communiceert met een groep nodes in het netwerk
	- <span style="color:#ffffbf;">Broadcast</span>: 1 node communiceert met alle andere nodes in het netwerk