# Partie 1_Old

## Exercice 1 - Reconnaissance de la cible

#### Consignes: Utiliser dig {collapsible="true"}
- Les IP des serveurs de nom de d'oteria (domaine oteria. fr).
- Les IP des serveurs de messagerie de d'oteria.
- Le FQDN du serveur web de l'école et les IP qui lui sont associées.

#### Réponses: Utiliser dig {collapsible="true"}

IP des serveurs de nom d'Oteria
: Récupération en utilisant l'utilitaire dig

: ```Bash
        dig oteria.fr
    ```

: ```Console
            ; DiG 9.16.48-Debian <<>> oteria.fr
            ;; global options: +cmd
            ;; Got answer:
            ;; -HEADER- opcode: QUERY, status: NOERROR, id: 64817
            ;; flags: qr rd ra; QUERY: 1, ANSWER: 2, AUTHORITY: 0, ADDITIONAL: 1
            
            ;; OPT PSEUDOSECTION:
            ; EDNS: version: 0, flags:; udp: 4096
            ;; QUESTION SECTION:
            ;oteria.fr.			IN	A
                        
            ;; ANSWER SECTION:
            oteria.fr.		4335	IN	A	99.83.190.102
            oteria.fr.		4335	IN	A	75.2.70.75
                        
            ;; Query time: 10 msec
            ;; SERVER: 198.19.248.200#53(198.19.248.200)
            ;; WHEN: Mon Feb 19 14:25:41 CET 2024
            ;; MSG SIZE  rcvd: 88
    ```

IP des serveurs de messagerie d'Oteria
: Récupération en utilisant l'utilitaire dig

: ```Bash
    dig oteria.fr MX
    ```

: ```Console
    ; <<>> DiG 9.16.48-Debian <<>> oteria.fr MX
    ;; global options: +cmd
    ;; Got answer:
    ;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 43949
    ;; flags: qr rd ra; QUERY: 1, ANSWER: 5, AUTHORITY: 0, ADDITIONAL: 1
    
    ;; OPT PSEUDOSECTION:
    ; EDNS: version: 0, flags:; udp: 4096
    ;; QUESTION SECTION:
    ;oteria.fr.			IN	MX
    
    ;; ANSWER SECTION:
    oteria.fr.		4167	IN	MX	5 alt1.aspmx.l.google.com.
    oteria.fr.		4167	IN	MX	1 aspmx.l.google.com.
    oteria.fr.		4167	IN	MX	10 alt3.aspmx.l.google.com.
    oteria.fr.		4167	IN	MX	5 alt2.aspmx.l.google.com.
    oteria.fr.		4167	IN	MX	10 alt4.aspmx.l.google.com.
    
    ;; Query time: 18 msec
    ;; SERVER: 198.19.248.200#53(198.19.248.200)
    ;; WHEN: Mon Feb 19 14:38:08 CET 2024
    ;; MSG SIZE  rcvd: 273
    ```

FQDN du serveur web de l'école et les IP qui lui sont associées.
: Récupération en utilisant l'utilitaire dig

: ```Bash
    dig oteria.fr MX
    ```