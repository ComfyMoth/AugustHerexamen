# Waar type je de commando's in
in CMD!
1. recht-klik  op de windows knop
![[Pasted image 20240716140357.png]]
2.  Klik op de uitvoeren knop
![[Pasted image 20240716140741.png]]
3. Type 'CMD'
![[Pasted image 20240716140829.png]]
4. Nu kan typen
![[Pasted image 20240716140847.png]]

# Command list
## PING (ip adress of domain)
Geeft informatie over hoe lang een pakketje nodig heeft om bij dat ip adress te raken en terug
![[Pasted image 20240716135743.png]]

## Traceroute (ip adress of domain)
Gelijkaardig aan [[Netwerk CheatSheet#Command list#PING (ip adress of domain)|PING]] maar toont alle nodes die het pakketje is gepasseerd opweg naar dit ip / domein
![[Pasted image 20240716135929.png]]

## NSlookup (ip adres of domain)
Toont informatie over de DNS server waar de pc mee is verbonden. Kan ook gebruikt worden om te zien welk ip aan een bapaald domein hangt en vice versa. Kan ook gebruikt worden om specifiek via bepaalde DNS server dit op te vragen

voorbeeld:
![[Pasted image 20240716140927.png]]
## IPconfig
Toont details van eht netwerk waarmee je verbonden bent. Dit bevat vb je ip, je subnet mask en de fault gateway

voorbeeld:
![[Pasted image 20240716140949.png]]
(meer naar onder staan de wifi & ethernet)
## Netstat
Geeft een zicht over de poorten die open staan op jou PC en UDP/TCP statistieken. Ook zicht over TCP-connecties die actief zijn
![[Pasted image 20240716141352.png]]
(ip adresses are hidden for privacy)

# Netmask berekenen
## klasses
[[05. Netwerklaag IPv4#indeling van IPv4 adressen in klasses|Indeling van IPv4 adressen in klasses]]
![[Pasted image 20240720140331.png]]
## Classfull adressing
<span style="color:#c8ab83;">classful adresseren</span> = Gebruik maken van IPv4 adressen in combinatie met het standaard netmask dat bij hun klasse hoort

Bij classful adressering komen we op die manier tot volgende getallen:
![[Pasted image 20240720145208.png]]