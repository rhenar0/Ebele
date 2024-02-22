# Partie 1 - Collecte d’informations

## Exercice 1 - Reconnaissance de la cible

### Utiliser 'dig' {collapsible="true"}

#### Consigne
- Quel peut être l'intérêt d'avoir plusieurs IP associées à un seul nom pour un serveur web ?

#### Réponse
- L'intérêt d'avoir plusieurs IP peut se trouver dans la distrubtion du trafic entrant sur plusieurs adresses IP. Ceci permet de répartir la charge de manière équilibrée entre plusieurs serveurs ou instances de serveurs web. Cela permet d'optimiser les performances du site web en répartissant la charge de manière équilibrée.

### Utiliser 'whois' {collapsible="true"}

#### Consignes {id="consignes_1"}
- Quel est le serveur whois qui a répondu ?
- Quel est le nom du registrar (l'organisme qui a enregistré le nom de domaine) ?
- Quelles informations sont utiles pour obtenir davantage d'informations sur le SI ou le personnel de l'université ?

#### Réponses {id="r-ponses_1"}

Résultat du 'whois' et du serveur associé répondant :
: ```Console 
    nserver:                       dns15.ovh.net
    nserver:                       ns15.ovh.net
    source:                        FRNIC
    ```

Nom du registrar et ses informations :
: ```Console
    registrar:                     OVH
    address:                       2 Rue Kellermann
    address:                       59100 ROUBAIX
    country:                       FR
    phone:                         +33.899701761
    fax-no:                        +33.320200958
    e-mail:                        support@ovh.net
    website:                       http://www.ovh.com
    anonymous:                     No
    registered:                    1999-10-18T00:00:00Z
    source:                        FRNIC
    ```

Informations utiles sur le SI et le personnel de l'école :
: ```Console
    nic-hdl:                       GI8908-FRNIC
    type:                          ORGANIZATION
    contact:                       Groupe IKAÏ
    address:                       Groupe IKAÏ
    address:                       23 rue blanche
    address:                       75009 paris
    country:                       FR
    phone:                         +33.603410367
    e-mail:                        fblj14nmlo548i18tsej@s.o-w-o.info
    registrar:                     OVH
    anonymous:                     NO
    obsoleted:                     NO
    eppstatus:                     associated
    eppstatus:                     active
    eligstatus:                    not identified
    reachstatus:                   not identified
    source:                        FRNIC
    ```

### Utiliser 'whois' sur 'wikipedia.org' {collapsible="true"}

#### Consigne {id="consigne_1"}
- Y-a-t-il des informations utiles pour obtenir davantage d'informations sur le SI ou le personnel de wikipedia ?

#### Réponse {id="r-ponse_1"}
- Wikipedia utilise un système pour privatiser ses informations et ne laisser transparaitre aucune informations personnels. Ce service est par exemple disponible chez OVH sous le nom de OWO.

### Utiliser 'whois' sur une IP {collapsible="true"}

#### Consigne {id="consigne_2"}
- Quel est l'adresse du réseau de cette IP (champ inetnum ou NetRange)?

#### Réponse {id="r-ponse_2"}
L'adresse IP d'Oteria ramène sur cette adresse réseau :
: `NetRange:       99.83.64.0 - 99.84.255.255`

### Découverte d'hôtes basé sur le protocole DNS {collapsible="true"}

#### Consignes {id="consigne_3"}
- Quelles sont les types d'enregistrements DNS trouvés (A, NS, CNAME, ...)?
- Le site web gamekult fait appel à plusieurs compagnies pour héberger ses services. Lesquelles?
- Quelle compagnie posséde les serveurs DNS faisant autorité sur gamekult . com?
- Quelle compagnie posséde les serveurs d'envoi de mails vers des adresses en @gamekult . com?
- Quelle compagnie posséde le serveur web www. game kult. com?
- Quel est l'intérêt pour gamekult, en terme de sécurité, d'avoir autant d'hébergeurs ?


#### Réponses {id="r-ponse_3"}
##### Les types d'enregistrements DNS trouvés {collapsible="true"}
DNS Servers
: matt.ns.cloudflare.com. - 172.64.33.131 - CLOUDFLARENET - United States
: roxy.ns.cloudflare.com. - 108.162.192.142 - CLOUDFLARENET - United States

MX Records ** This is where email for the domain goes...
: 1 aspmx.l.google.com. - 172.253.122.27 - GOOGLE - United States
: 10 aspmx2.googlemail.com. - 209.85.202.27 - GOOGLE - United States
: 10 aspmx3.googlemail.com. - 64.233.184.27 - GOOGLE - United States
: 5 alt1.aspmx.l.google.com. - 209.85.202.27 - GOOGLE - United States
: 5 alt2.aspmx.l.google.com. - 64.233.184.26 - GOOGLE - United States

TXT Records ** Find more hosts in Sender Policy Framework (SPF) configurations
: "google-site-verification=lxjRphsDPTk_R79fe1pw80G8etEHp9Kq5R41VmPaNlw"
: "google-site-verification=oHd3mFX17KI3dvhYAjMALWy-4y2TD4Mj8w2_3ejFkzI"
: "v=spf1 include:amazonses.com ~all"
: "v=spf1 include:spf.mailjet.com ?all"

Host Records (A) ** this data may not be current as it uses a static database (updated monthly)
: img2.gamekult.com
: HTTP: cloudflare - 172.67.68.72 - CLOUDFLARENET - United States
: jeux-flash.gamekult.com
: HTTP: Apache - HTTP TECH: varnish - 95.131.141.52 - not.updated.oxalide.net - OXALIDE - France

: nl.gamekult.com
: HTTP: Apache - HTTP TECH: varnish - 95.131.141.52 - not.updated.oxalide.net - OXALIDE - France

: premium.gamekult.com 
: 91.220.85.88 - ut-lb.pilotsystems.net - PILOTSYSTEMS-AS - France

: cdn.gamekult.com
: HTTP: cloudflare - 172.67.68.72 - CLOUDFLARENET - United States - www.gamekult.com - 91.220.85.88 - ut-lb.pilotsystems.net - PILOTSYSTEMS-AS

