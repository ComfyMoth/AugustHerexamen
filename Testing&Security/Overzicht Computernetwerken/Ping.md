# ICMP
Het programma `ping` is een veelgebruikt netwerkdiagnostisch hulpmiddel dat helpt bij het testen van de connectiviteit tussen twee nodes in een netwerk. Het gebruikt het Internet Controle Message Protocol (<span style="color:#c8ab83;">ICMP</span>) om echo-verzoeken te sturen naar een doelhost en luistert naar echo-antwoorden. 
Hierdoor kunnen gebruikers de beschikbaarheid en de reactietijd van het doelsysteem beoordelen.

# Gebruik 
je kan een hostnaam of IP-adres als volgt pingen:
- `ping www.ap.be` (hostnaam)
- `ping 192.168.0.100` (IP-adres)

# Uitvoer
Als het lukt een netwerknode te pingen, krijg je meerdere replies. Dit komt omdat één vraag-antwoordcyclus (of "<span style="color:#c8ab83;">round trip</span>") niet altijd betrouwbare informatie biedt:
![](https://apwt.gitbook.io/~gitbook/image?url=https%3A%2F%2F3283203901-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FKrXKbRoPmGxyrXNQktCY%252Fuploads%252Fgit-blob-131c84be249b60542093f210a7a5f34150a9913d%252Fping.png%3Falt%3Dmedia&width=768&dpr=4&quality=100&sign=e323fbe7&sv=1)