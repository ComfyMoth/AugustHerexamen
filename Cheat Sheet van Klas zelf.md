# Cheat sheet

Naast onderstaande commando’s mag je gebruik maken van:

- Docker plugin Visual Studio Code
- Web interface van Github Actions, officiële documentatie van specifieke actions, kant-en-klare workflows die worden voorgesteld onder “Actions”
- De ingebouwde `--help` vlag van `faas-cli` en van subcommando’s hiervan
- De online OpenFaaS (`https://jaws2paws.com`)

Alle andere bronnen, ook oude oefeningen en de cursus, zijn verboden.

## Docker

```
FROM <naam van de base image>:<optionele tag> # spreekt voor zichzelf
WORKDIR <folder> # kies de map in de image waarin je werkt
COPY <van> <naar> # kopieer files van de bronmachine naar de image
RUN <commando> # voer commando uit tijdens de build
EXPOSE <port> # geef aan dat de image luistert op deze poort
CMD <commando> # voer commando uit wanneer de container start, eventueel geschreven als lijst
docker ps # toon alle lopende containers
docker ps -a # toon alle containers, ook de gestopte
docker logs <containernaam> # toon logfile van een container
docker exec -it <containernaam> sh # start shell op in lopende container, nuttig voor troubleshooting
docker container --help
docker run --help
docker image --help
docker build --help
docker push --help
docker login --help
docker tag --help
sleep <aantalseconden>
```

## Docker Compose

Vertrekpunt: `docker-compose --help`. Belangrijke keys voor `docker-compose.yml`:

- `version`
- `services`
- `ports`
- `build`
- `image`
- `depends_on`
- `environment`
- `volumes` (als onderdeel van een service)
- `volumes` (buiten services)

## Github Actions

- web UI van Github

## Serverless

- Alle commando’s voor faas: `faas-cli --help`

### Stack file

- Omgevingsvariabelen: key `environment`, zelfde syntax als voor Docker Compose.
- Secrets: key `secrets`, value lijst met strings (één waarde per secret).

### Omgevingsvariabele uitlezen in NodeJS

`process.env.NAAMVANDEVARIABELE`

### Secrets uitlezen

```
// ingebouwde functionaliteit van NodeJS voor asynchrone file handling
const { readFile } = require('fs').promises;
module.exports = async(event, context) => {

// misschien nog wat code
// elk secret wordt opgevraagd via het filesysteem van de container van de functie
const secret1 = await readFile("/var/openfaas/secrets/secret1");
const secret2 = await readFile("/var/openfaas/secrets/secret2");

// rest van de code
// bovenstaande variabelen zullen van het type Buffer zijn, maar je kan ze omzetten naar strings via .toString()
```

### Binaire data

- `base64 -w 0 NAAM_VAN_BINAIR_BESTAND`
- `base64 --decode NAAM_VAN_TEKSTBESTAND > NAAM_VAN_BINAIR_BESTAND`
- `Buffer.from("ABCD...","base64")`
- `buffer.toString("base64')`

### faasd gebruiken in Github Actions

```
# nodig om commando's te kunnen uitvoeren
- name: Download and install faas-cli
  run: curl -sLSf https://cli.openfaas.com | sudo sh
# vereist om Docker images te kunnen bouwen
- name: Set up QEMU
  uses: docker/setup-qemu-action@v2
- name: Set up Docker Buildx
  uses: docker/setup-buildx-action@v2
# bouwen van de functie zoals je dat lokaal doet
- name: Build function only
  run: faas-cli build -f image-processing.yml
```

# Mogelijke examenvragen

## Docker images

Je moet een alle commando’s in de cheat sheet beheersen en kunnen toepassen om zaken te bereiken die je ook lokaal zou kunnen.

Tip: als een container meteen crasht, kan je het commando vervangen door `sleep 1000` zodat je kan inloggen en dingen uitproberen.

### Voorbeeld

Je krijgt een C♯-programma. Maak een Docker image met een naam naar keuze waarin dit programma draait. Gebruik de image `bitnami/dotnet-sdk:latest`. Tag je eigen image als volgt: `docker tag <imagenaam> <dockerhubusername>/<imagenaam>`. Zet hem dan op Docker Hub. Hou alle nodige stappen bij in een tekstbestand. Je levert alle noodzakelijke bronfiles in, _samen_ met dit tekstbestand. Lokaal kan je dit project runnen met `dotnet run`.

## Docker Compose

Je moet een app kunnen bouwen waarin verschillende containers samenwerken om één geheel aan te bieden.

### Voorbeeld

Je krijgt de Node-broncode van een Node/Express/MongoDB applicatie en je hoeft niets rechtstreeks met MongoDB te doen. Je moet samen hiermee een MongoDB container (basisimage `mongo`) opstarten met omgevingsvariabelen `MONGO_INITDB_ROOT_USERNAME` en `MONGO_INITDB_ROOT_PASSWORD`. Een container voor deze image luistert vanzelf op poort 27017. Schrijf een Docker Compose file waarmee je deze applicatie volledig lokaal kan uitvoeren, zodat je bericht krijgt dat de voorbeelddata is opgeslagen. Het enige dat je mag aanpassen aan de JavaScriptcode is de connectie-URL. De data hoeft geen herstart van de container te overleven.

## Github Actions

Je moet weten hoe je workflows aanmaakt en hoe je actions toevoegt, ook als dit actions zijn die niet expliciet aan bod zijn gekomen in de cursus (op voorwaarde dat je de nodige technische achtergrond wel hebt).

### Voorbeeld

Schrijf een workflow voor een gegeven NodeJS-project. Voor dit project moet een Docker image gebouwd worden en hij moet gepubliceerd worden naar een Docker repository (GHCR of Docker Hub). Nadat de image gebouwd is, moet je jezelf een e-mail sturen. Dit doe je met met de action `hilarion5/send-mail`.

Je kan een open SMTP server gebruiken. [Hier](https://www.wpoven.com/tools/free-smtp-server-for-testing) is er een omschreven, waarvoor je geen usernaam of wachtwoord nodig hebt. Je kan wel zien of je workflow geslaagd is op Github.

## Serverless functions

Je moet weten hoe je serverless functies aanmaakt en deployt met faasd. Je moet dit “from scratch” kunnen doen. Met andere woorden, als je een foutmelding krijgt omdat je ergens niet de rechten hebt om een push of pull te doen, moet je zelf kunnen achterhalen welke extra stappen vereist zijn om dit op te lossen. Je moet deze functie ook kunnen deployen, zowel op je eigen installatie als op de backup installatie die online staat (`https://jaws2paws.com`). Functies moeten overweg kunnen met plain text data en met binaire data (via base64). Je moet ook weten hoe je authenticatie voorziet, zoals hoe we dat in de les hebben gedaan.

Je moet de verschillende commando’s die je nodig hebt documenteren en hun betekenis telkens in één zin verklaren in een tekstbestand. Je levert alle bronfiles in, _samen_ met dit tekstbestand.

Er staat niets op de cheat sheet rond faasd commando’s, maar de vlag `--help` werkt voor zowel `faas-cli` als voor subcommando’s.

### Voorbeeld

Schrijf een serverless functie om CSS te “minifyen” op basis van de `node18`-template. Je gebruikt hiervoor de library `csso` (versie 5.0.5). Onderstaand voorbeeld is voldoende om je op weg te helpen:

```
import { minify } from 'csso';
// CommonJS is also supported
// const { minify } = require('csso');

const minifiedCss = minify('.test { color: #ff0000; }').css;

console.log(minifiedCss);
```

In de web UI zou de verkleinde CSS moeten verschijnen in de response body.