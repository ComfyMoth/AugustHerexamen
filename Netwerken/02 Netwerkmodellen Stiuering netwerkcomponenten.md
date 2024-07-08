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
- Elke set van regels en afspraken noemen we een protocol
- Per laag kunnen meerdere protocols actief zijn

## Nut van een lagenmodel
- Maakt complexe systemen begrijpelijk
- Maakt de relaties tussen de onderdelen van het geheel duidelijk
- Laat discussie toe waarbij iedereen weet waarover het gaat
- Laat uitbreiding en verbetering sneller verlopen
- Maakt dat een aanpassing op 1 gebied van de dienstverlening niet het volledige geheel verstoort of platlegt
	- Modulaire opbouw van een complex geheel
- Het model volgen geeft minder kans op fouten of vergetelheden
- Het model volgen geeft snellere resultaten bij het lokaliseren en oplossen van problemen

# Theoretische referentie: ISO / OSI model
![[Pasted image 20240708164232.png]]

- <span style="color:#ffb1af;">Applicatie laag</span>: beschrijft het gedrag van netwerk applicaties
- <span style="color:#ffdfbe;">Presentatie laag</span>: beschrijft de interpretatie van data (encryptie, compressie, codecs)
- <span style="color:#ffffbf;">Sessie laag</span>: beschrijft het opzetten van verbindingen, het synchroniseren van de data stroom, het controleren van de data
- <span style="color:#b4f0a8;">Transport laag</span>: beschrijft de proces naar proces data-overdracht binnen een toestel
- <span style="color:#a9d0f7;">Netwerk laag</span>: beschrijft de adressering van hosts op een netwerk en de routering van data van bron tot bestemming
- <span style="color:#cc99fe;">Datalink laag</span>: beschrijft de data overdracht tussen naburige [[01 Introductie en Overview Netwerkopbouw#LAN|LAN]] elementen
- <span style="color:#e4569e;">Fysieke laag</span>: beschrijft bits, fysieke signalen en fysieke media

# Echte Protocolstack: TCP / IP model