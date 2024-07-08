[Presentatie](https://learning.ap.be/pluginfile.php/1957755/mod_resource/content/3/02%20-%20Theorie%20-%20Netwerkmodellen.pdf)
# Waarom een model maken?
- Een netwerk kan heel groot en complex zijn
- Een netwerk bestaat uit veel onderdelen
	- Hosts (end devices)
	- Switches (connectivity device / transit node)
	- Routers
	- Verschillende soorten fysieke verbindingen met elk andere eigenschappen
	- Applicaties
	- Protocols
	- ...
- Door de vele onderdelen is het lastig om een overzicht te houden
	- Geen overzicht = meer kans op fouten en vergetelheden
	- Geen overzicht = langer werk om problemen te vinden en op te lossen

# Lagenschema - Protocolstack
Kunnen we de structuur van een netwerk in een soort universeel model gieten om alles overzichtelijk te houden?
- Gelukkig wel
- Modellen die je stap voor .stap kan volgen en een ontvanger in orde te krijgen
- Modellen in de vorm van een <span style="color:#c8ab83;">lagenschema</span>
- Op elke laag van het schema zijn andere protocollen actief / gelden er andere afspraken
- Zo een lagenschema noemt men dus ook wel eens <span style="color:#c8ab83;">protocolstack</span>

## Voorbeeld van een lagenschema uit leefwereld
Van thuis tot op je reisbestemming geraken met het vliegtuig
![[Pasted image 20240708163705.png]]
## Dienstverlening binnen een lagenmodel
- Elke laag verschaft andere diensten
- Alle diensten zijn nodig om de communicatie (de reis in ons voorbeeld) te laten lukken
- Elke dienst heeft eigen interne regels en procedures
- Elke laag is afhankelijk van de dienstverlening van de aangrenzende lagen
	- Elke laag werkt heeft de dienstverlening van de vorige laag nodig
	- Elke laag verschaft nuttige diensten voor de volgende laag
- De dienstverlening = software die geschreven is en die bepaalde regels volgt
- Elke set van regels en afspraken noemen we een protocl