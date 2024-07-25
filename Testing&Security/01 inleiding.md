# 1. Overzicht

# 2. Introductie
## 2.1 Software Development Life cycle (SDLC)
(1)
![](https://apwt.gitbook.io/~gitbook/image?url=https%3A%2F%2F4058530821-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-legacy-files%2Fo%2Fassets%252Fg-pro-software-testing%252F-MHfjgKptfnQJ_1d1SgM%252F-MHfk9GvAchlxMUgTNv3%252F1.png%3Fgeneration%3D1600609364187874%26alt%3Dmedia&width=768&dpr=4&quality=100&sign=20b7fe64&sv=1)
(2) waterval model
![](https://apwt.gitbook.io/~gitbook/image?url=https%3A%2F%2F4058530821-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-legacy-files%2Fo%2Fassets%252Fg-pro-software-testing%252F-MHfjgKptfnQJ_1d1SgM%252F-MHfk9Gw11z3AAlbiQqn%252F2.png%3Fgeneration%3D1600609364188326%26alt%3Dmedia&width=768&dpr=4&quality=100&sign=2d81648f&sv=1)
(3) Iteratief model
![](https://apwt.gitbook.io/~gitbook/image?url=https%3A%2F%2F4058530821-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-legacy-files%2Fo%2Fassets%252Fg-pro-software-testing%252F-MHfjgKptfnQJ_1d1SgM%252F-MHfk9Gx4bShjxC-_AaW%252F3.png%3Fgeneration%3D1600609364225218%26alt%3Dmedia&width=768&dpr=4&quality=100&sign=e5b71a6a&sv=1)

Hierboven vind je enkele van de vele voorstellingen van **software development life cycle** en de implementatie hiervan. 
Afbeelding 2 is een afbeelding van de waterval model, waar elke fase volledig wordt doorlopen en goedgekeurd alvorens aan de volgende fase te beginnen.
Afbeelding 3 is een afbeelding van een iteratief model, waar dezelfde fasen verschillende keren na elkaar worden uitgevoerd. D

Wat wordt afgebeeld strookt ook niet met het concept dat vanaf dag 1 'getest' worden. De fase testen hierboven handelt over het testen van code. hier ligt ook onze focus.

## 2.2 Software testing life cycle
![](https://apwt.gitbook.io/~gitbook/image?url=https%3A%2F%2F4058530821-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-legacy-files%2Fo%2Fassets%252Fg-pro-software-testing%252F-MHfjgKptfnQJ_1d1SgM%252F-MHfk9Gy8t3SCitj_a4F%252F4.png%3Fgeneration%3D1600609364178067%26alt%3Dmedia&width=400&dpr=2&quality=100&sign=548446f8&sv=1)
Hier volgt een korte beschrijving van de verschillende fasen:
### 2.2.1 Specificatie analyse
In deze stap zullen test teams de specificaties onder de loep nemen en de testbare behoeften identificeren.
Deze kunnen zowel functioneel als niet-functioneel zijn. 
In deze fasen wordt ook de prioriteit bepaald en wordt de testomgeving vastgelegd.

### 2.2.2 Test planning
In deze stap wordt het test plan (document) opgesteld. In dit plan vind je onder meer welke soorten testen (zie later) zullen worden uitgevoerd, wordt beschreven wat de scope en het doel is van de software, de te gebruiken testtools gekozen, de rapportering vastgelegd, ...

### 2.2.3 Test case ontwikkeling
In deze stap wordt de test cases en test scripts ontwikkeld en gevalideerd. Ook de test data wordt opgezet

### 2.2.4 Opzetten van de testomgeving
De testomgeving is een geheel van software en hardware waarop de testen kunnen worden uitgevoerd. De omgeving bepaalt mee onder welke voorwaarden de testen worden uitgevoerd

### 2.2.5 Het uitvoeren van testen
In deze fase wordt het proces van het uitvoeren van de code en het vergelijken van de verwachte en actuele resultaten uitgevoerd. Belangrijk is het registreren van de resultaten (de status van een test wordt aangeduid met "Pass-geslaagd", "Fail-gefaald", "Blocked-geblokkeerd", "Not Run-niet uitgevoerd", ...) en dat voor niet geslaagde testen een defecten rapport wordt opgesteld waarin beschreven wordt wat er precies mis loopt.

### 2.2.6 Het afsluiten van de test cyclus
Dit is de vergelijking van de testresultaten ten opzichte van de kwaliteitscriteria en het eventueel uiteindelijk vrijgeven van de software. Het resultaat van deze fase is een Finaal defecten rapport. Verder worden de test cases herbekeken, worden de test cases en de test data schoongemaakt en wordt ook het testproces op zich bekeken.

## 2.3 Wat is een bug? Waarom komen bugs voor?
Een software bug is een fout in een computer programma of systeem die de oorzaak is dat het programma of systeem een onverwacht of onjuist resultaat geeft of onbedoeld gedrag uitvoert.

De bronnen van bugs zijn divers:
1. Niet duidelijke specificaties, vaak door miscommunicatie of een klant die nog niet volledig weet wat de software moet en niet moet doen.
2. Constant veranderende specificaties ook gekend als het "moving target probleem"
3. Het verbeteren van een bug die andere bugs introduceert
4. Design en redesign van vb. de user interface
5. Fundamentele problemen eigen aan software design en architectuur
6. Herschikken van resources, herwerken of weglaten van stukken code
7. Veranderingen in hard-/software (belangrijk in langdurende projecten - releaseverhogingen van gebruikte software)
8. Het naderen van de deadline(snel, snel, snel, ...)
9. Complexiteit van het bug-tracking proces

## 2.4 Bug life cycle
De bug life cycle start met een onbedoelde gemaakte fout en eindigt wanneer deze fout is opgelost. Deze life cycle bestaat uit een aantal fasen / statussen:
![](https://apwt.gitbook.io/~gitbook/image?url=https%3A%2F%2F4058530821-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-legacy-files%2Fo%2Fassets%252Fg-pro-software-testing%252F-MHfjgKptfnQJ_1d1SgM%252F-MHfk9GzxUV8yHo3RmAy%252F5.png%3Fgeneration%3D1600609364222818%26alt%3Dmedia&width=400&dpr=2&quality=100&sign=fcc66f1b&sv=1)

![](https://apwt.gitbook.io/~gitbook/image?url=https%3A%2F%2F4058530821-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-legacy-files%2Fo%2Fassets%252Fg-pro-software-testing%252F-MHfjgKptfnQJ_1d1SgM%252F-MHfk9H-GZTniSIErqe0%252F6.png%3Fgeneration%3D1600609364259378%26alt%3Dmedia&width=768&dpr=4&quality=100&sign=43ce35bd&sv=1)

## 2.5 De kost van het oplossen van bugs
De kost voor het oplossen van bugs stijgt exponentieel; De verklaring hiervoor is:
- Het is veel eenvoudiger om fouten te vinden wanneer er nog ontwikkeld wordt. De ontwikkelaar "zit nog in de code". Wanneer de software is opgeleverd en de ontwikkelaar werkt aan andere software is dat niet meer zo. Een fout die door de ontwikkelaar wordt gevonden en opgelost heeft een beperkte kost
- Wanneer men begint aan het formele testen wordt de kost groter. Het is de tester die de fout vindt en de fout beschrijft, het testproces wordt doorlopen, rapporten moeten gemaakt worden, tijd