# Partie 3 - Scan de réseaux avec nmap

## Exercice 2 - Découvertes d'hôtes

### Utiliser 'NMAP' {collapsible="true"}
![image.png](image.png)

Le fonctionnement de cette technique
: Envoie des paquets ARP  aux hôtes du réseau pour déterminer s'ils sont actifs.

Les paquets ARP
: Les paquets ARP utilisent la découverte du réseau basé sur le broadcast via l'adresse MAC, ils ne peuvent donc être 
utilisé seulement sur le même domaine de broadcast.

## Exercice 3 - Balayages SYN et connect

### Le fonctionnement de SYN {collapsible="true"}
![image_1.png](image_1.png)

La différence
: Le -sT fait le handshake au complet du TCP contrairement au -sS.

Les avantages
: SYN est plus discret puisqu'il n'établit pas toute la connexion, il vérifie seulement la disponibilité de l'host.

## Exercice 4 - Balayages Xmas, Fin et Nul

### Le fonctionnement de XMAS {collapsible="true"}

Le balayage
: Lorsque nmap effectue un balayage Xmas, il envoie des paquets TCP avec les drapeaux FIN, URG et PSH activés. 
Ces paquets sont souvent utilisés pour sonder un système à la recherche de ports ouverts.
Les états de port constatés par nmap lors du balayage Xmas peuvent être "open" (ouvert), "closed" (fermé) ou "filtered" (filtré). 
Si un port est ouvert, le système répondra différemment aux paquets Xmas comparé à un port fermé ou filtré.

### Le fonctionnement de FIN {collapsible="true"}

Le balayage
: Le balayage Fin est une technique similaire au balayage Xmas, mais dans ce cas, seul le bit FIN est activé dans le paquet TCP. Cela est souvent utilisé pour découvrir des ports ouverts sur un système.
Les états de port constatés par nmap lors du balayage Fin peuvent être similaires à ceux du balayage Xmas : "open", "closed" ou "filtered".

### Le fonctionnement de NULL {collapsible="true"}

Le balayage
: Le balayage NULL est une technique où aucun bit de contrôle n'est activé dans les paquets TCP. Cela peut également être utilisé pour détecter des ports ouverts sur un système.
Les états de port constatés par nmap lors du balayage NULL sont similaires à ceux des autres balayages : "open", "closed" ou "filtered".

### En résumé {collapsible="true"}

Avantages
: Furtivité : Ces balayages peuvent être plus discrets que les balayages SYN et connect, car ils ne complètent pas l'établissement complet d'une connexion TCP.
Détection de pare-feu : Certains pare-feu peuvent réagir différemment à ces types de balayages, permettant de détecter leur présence.

Inconvénients
: Fiabilité : Certains systèmes et pare-feu peuvent être configurés pour ignorer ou répondre de manière incohérente à ces balayages, rendant les résultats moins fiables.
Possibilité de faux positifs : Certains services peuvent répondre de manière similaire, indépendamment du fait que le port soit ouvert ou fermé, conduisant à des faux positifs.
En général, le choix entre ces techniques de balayage dépend du contexte spécifique de la situation et des caractéristiques du réseau cible.

## Exercice 5 - Balayage ACK

Lorsqu'un firewall est activé sur l'hôte cible alors la réponse diffère entre "filtred"/"unfiltred"

Analyse
: Cette analyse est différente des autres analysées jusqu'à présent, car elle ne détermine jamais les ports ouverts (ou même ouverts|filtrés). Il est utilisé pour cartographier les règles des pare-feux, en déterminant s'ils sont à état ou non et quels ports sont filtrés. Le paquet de sonde d'analyse ACK n'a que l'indicateur ACK (sauf si vous utilisez --scanflags). Lors de l'analyse de systèmes non filtrés, les ports ouverts et fermés renverront tous deux un paquet RST. Nmap les marque alors comme non filtrés, ce qui signifie qu'ils sont atteignables par le paquet ACK, mais que le fait qu'ils soient ouverts ou fermés est indéterminé. Les ports qui ne répondent pas ou qui renvoient certains messages d'erreur ICMP (type 3, code 1, 2, 3, 9, 10 ou 13) sont étiquetés comme filtrés.

## Exercice 6 - Prise d’empreinte TCP/IP

Résumé d'analyse
: OS details: Linux 4.15 - 5.8 | Le code de retour du test est : CD=S | La cible de répond pas correctement, la valeur correcte est 0 ce qui est représenté par le Z sur nmap.

## Exercice 7 - Détection de versions

Le test NULL
: Le nom du test est NULL

Le test GetRequest
: Le nom du test est : GetRequest  ,est une méthode courante pour la reconnaissance de services pendant la phase de scan de Nmap, la sonde est configurée pour envoyer une requête GET vide (c'est-à-dire "\r\n\r\n") sur le port TCP spécifié. La réponse du service est ensuite analysée pour identifier le type de service.

