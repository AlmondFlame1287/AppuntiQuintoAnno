# Livelli Applicazione

---

Il livello piu' alto del protocollo **ISO/OSI**.

Implementa vari tipi di protocolli:

- POP3 - per la posta
- FTP - per il trasferimento dei file
- [HTTP](./LivelliApplicazione.md#http) - per le pagine web
- DNS - per trasformare i nomi dei siti in indirizzi IP

Per le altre applicazioni invece si usano dei protocolli proprietari.

Implementano anche delle **API**, ovvero delle librerie che forniscono uno strato intermedio tra lo strato applicativo e lo strato di trasporto

Vi sono varie archittetture

- Client-server
- Peer-to-peer
  - Puro
  - Centralizzato
  - Ibrido
- Ibride

## Protocollo Telnet

---

Veniva usato per connettersi ad un altro computer in modalita' terminale su porta 23 con protocollo TCP

Alla base del protocollo c'e' il concetto di simmetria, ovvero si deve avere richiesta e risposta prima di poter fare altre operazioni.

## HTTP

---

Usato per connettersi alle pagine web.

### Come funziona?

Il browser recupera informazioni sul sito in base all['**URL**](./LivelliApplicazione.md#url), e se c'e' una risposta, il server apre una connessione sulla porta 80 dove manda tutte le informazioni della pagina web.

Secondo le regole del protocollo la comunicazione e' formata da richiesta e risposta. Il meccanismo si dirama in:

1. Apertura connessione TCP
2. Browser chiede una risorsa attraverso il [Socket](../Tepsit/Tepsit5A.md#socket)
3. Il server risponde

   - Con una risposta positiva
   - Con un messaggio di errore

4. Connessione stabilita/chiusa

I messaggi vanno da 100 a 599:

- Da 100 a 199: Risposta in fase di elaborazione
- Da 200 a 299: Successo
- da 300 a 399: Risorse spostate
- da 400 a 499: Risorsa incompleta/non trovata
- da 500 a 599: Problema col server

## URL

---

Serve per localizzare le risorse all'interno di un server

Un esempio di indirizzo URL **https://www.google.it/search** viene tradotto dal DNS, il quale lo trasforma in un indirizzo IP, ed e' formato da:

- Protocollo - HTTP, FTP
- Indirizzo - google.it
- Pathname - search

## Proxy

---

E' un server per il quale **transita il traffico di rete** per darci varie funzionalita'. La maggior parte delle volte si utilizza come **cache**.

## Cookies

---

Informazioni che il sito web salva sul nostro computer. Possono essere usati per **scopi utili** e per **scopi pubblicitari**.

# Crittografia

---

### Cos'e'?

La crittografia e' un sistema che permette di trasformare dei caratteri in altri, permettendo cosi' di trascrivere un messaggio segreto.

### Cosa significa cifratura?

La cifratura e' quel processo che permette di tradurre i messaggi in messaggi segreti

### Come funziona la crittazione simmetrica?

In base ad un algoritmo, il testo in entrata viene trasformato seguendo alcune regole, note sia al mittente che al destinatario. Questo permette sia la crittazione del testo, sia la decrittazione.

Un esempio di prima cifratura nella storia e' il "Cifrario di Cesare", il quale spostava di una o piu' lettere il messaggio. Per capirci, invece di scrivere A, questo scriveva B o C, e dunque una parola comprensibile tipo "ciao" diveniva "ekcq"

### Algoritmi di crittazione simmetrica

#### DES

Il DES e' uno degli algoritmi piu' anziani della crittografia simmetrica. E' basato su una chiave segreta di 64 bit, 8 di controllo e 56 utili. Il suo funzionamento e' abbastanza semplice:

1. Si suddivide il testo in blocchi da 8 byte
2. Si traspongono i 64 bit con la chiave da 56 bit
3. Per 16 volte, alcuni bit vengono sostituiti
4. Si traspongono i bit in modo inverso a quello iniziale

Questo sistema di crittografia venne ritenuto molto sicuro, fin quando nel 1998 venne abbattuto da un calcolatore costato solo 250k $

#### 3-DES

Nel 1999 venne introdotto il 3-DES, il quale usava 3 chiavi diverse e faceva passare il testo criptato in 3 algoritmi DES.

### Limiti della crittazione simmetrica

I limiti della crittazione simmetrica sono tanti, in quanto per criptare e decriptare un messaggio, sia il mittente che il destinatario devono avere la stessa chiave. Cio' significa che per essere in possesso della stessa chiave bisogna o mandarla tramite posta elettronica scomponendola in parti, cosa assolutamente non sicura perche' puo' essere sempre ricomposta, oppure andare di persona a consegnare la chiave. Questo la rende praticamente inutilizzabile in campo militare, dato che la chiave non puo' essere consegnata in maniera semplice e veloce.

## Le VLAN

---

### Cos'e'?

La VLAN e' un tipo di LAN che puo' essere divisa in modo da ridurre i costi, le collisioni e il traffico sulla rete. Ogni VLAN e' confinata al livello 2 mentre la comunicazione avviene al livello 3 del protocollo ISO/OSI.

### Quali sono i vantaggi di avere una VLAN?

I vantaggi sono i seguenti:

- Agilita' di manutenzione, in quanto la rete puo' essere gestita in remoto
- Riduzione del traffico, in quanto ogni rete virtuale possiede uno spazio a se' stante
- Economicita', poiche' non c'e' bisogno di comprare dei router e degli switch per dividere fisicamente la rete
- Scalabilita', in quanto si possono aggiungere e rimuovere terminali in una manciata di secondi
- Ottimizzazione delle infrastrutture
- Possibilita' di estensione

### Come possono essere realizzate le VLAN?

Vi sono principalmente due modi di realizzarle:

- Port-based VLAN
  - Si puo' comunicare con la VLAN solo tramite l'access port
- Tagged VLAN
  - Si possono utilizzare piu' VLAN su una sola interfaccia

### Come sono composte le VLAN?

Sono formate da:

- Un nome
- Un identificatore unico (VID)
- Un blocco di indirizzi IP

### Cosa sono le porte ibride?

Le porte ibride sono porte che devono essere utilizzate in modalita' tagged e untagged in modo da permettere allo switch di eseguire diverse operazioni:

- Port-ingress: deve riconoscere il tipo di VLAN di appartenenza
- Port-forwarding: si applicano le regole del forwarding e identifica la porta di uscita
- Port-egress: usata per inserire/rimuovere i tag

# Crittografia Asimmetrica

---

## Che succede se qualcuno intercetta il messaggio?

Il messaggio non puo' essere compreso, poiche' per decifrarlo serve la chiave privata.

## Quante modalita' di cifratura ci sono??

- **Confidenziale**
  - Chiave pubblica cripta, chiave privata decripta
  - Sono garantite la riservatezza e l'integrita' del messaggio.
- **Autenticazione**
  - Chiave privata cripta, chiave pubblica decripta
  - Garantisce l'integrita' e si e' sicuri del mittente del messaggio.
- **Ibrida**
  - Si usano entrambi i passaggi di cifratura e decifratura

### Che cos'e' un hash?

E' il calcolo di una stringa univoca che corrisponde unicamente ad un testo. Nel caso in cui anche solo una lettera fosse cambiata, l'**hash** sarebbe differente.

Algoritmi usati:

- MD5
- SHA256
- SHA512

## La firma digitale

E' basata su un sistema di codifica crittografica a chiavi asimmetriche.
Di solito e' un dispositov esterno, come una smart card, una business key.

### Come funziona?

- Si prende un documento
- Calcolo dell'[hash](./Sistemi5A.md#che-cose-un-hash)
- Si cifra con algoritmo asimmetrico
- Si invia il documento cifrato e firmato

## L'RSA

### Per cosa e' usato?

- Autenticita'
- La **non falsicabilita'** della frma
- La **non riutilizzabilita'** della firma
- La **non alterabilita'** della firma
- La **non ripudiabilita'** della firma

### Passaggi

- Scegliere due numeri primi $np1, np2$
- Calcolare n = $np1 * np2$
- Calcolare m = $(np1 - 1) * (np2 - 1)$
- Scegliere un numero $e < m$ coprimo
- Calcolare d = $1 \mod m \over e$
- Kpub = (e, n) Kpriv = (d, n)

### Cifratura

$m = 9$

$c = mcifrato = m^e = n$

---

# Sicurezza delle reti

## Cos'e' la sicurezza informatica?

Con sicurezza informatica si intende l'insieme dei prodotti, regole e protocolli per garantire la funzionalita' dei servizi durante delle catastrofi

## La CIA

- **C**: Confidenzialita' dei dati
- **I**: Integrita' dei dati
- **A**: Disponibilita' dei dati

## Minacce

Le minacce possono essere:

- **Naturali**:
  - Incendi
  - Terremoti
  - Tornadi
  - Agenti impossibili da prevenire
- **Umane**:
  - Attacchi interni:
    - Piu' pericolosi
    - Dipendenti malintenzionati
  - Attacchi esterni:
    - Attacchi spoofing
      - IP spoofing: qualcuno si sostituisce ad un host
      - Data spoofing: si inseriscono / modificano i dati durante il loro transito in rete
    - Packet sniffing
    - DoS - DDoS (Denial of Service)

## Aspetti principali

- **Autenticazione**
- **Autorizzazione**
  - Una volta autenticato, l'utente avra' dei diversi permessi.
  - Importante per la sicurezza
- **Riservatezza**
  - Informazioni leggibili solo agli utenti autorizzati
- **Disponibilita'**
  - Informazioni sempre disponibili, non importa cosa succede sul sistema
- **Integrita'**
- **Paternita'**
  - Ogni file e' associato ad un utente proprietario.
  - Usato per tenere traccia di alcuni fattori

## Valutazione dei rischi

In un'azienda che usa l'informatica in maniera pesante vi saranno due fasi essenziali:

1. Analisi dei rischi
   - Valutazione di alcuni rischi in base agli **asset**
   - Stima della probabilita' di alcuni eventi
2. Gestione della problematica

**Asset**: un qualsiasi bene dell'azienda

## Com'e' formato un attacco informatico?

**Obiettivo + Metodo + Vulnerabilita' = Attacco**

Obiettivo: oggetto da attaccare
Metodo: tipologia di attacco
Vulnerabilita': cosa sfruttare

### Tipi di attacchi in base al danno

- Attacchi dimostrativi
  - Non pericolosi, per dimostrare la bravura dell'hacker
- Attacchi criminali
  - Rubare i dati

### Tipi di attacchi Criminali in base alla partecipazione dell'hacker

- **Passivi**:
  - Sniffing
- **Attivi**:
  - Sostituzione di host
  - Produzione
    - Virus
    - Worm
    - Malware
  - Intrusione
  - Phishing

## I tre pilastri della sicurezza:

- **Prevenzione**
  - Connessioni tramite SSL
  - Firewall
  - VPN
- **Rilevazione**
  - monitoraggio e controllo degli accessi
- **Investigazione**
  - analisi dei dati rubati / danneggiati

---

# Sicurezza della posta elettronica

## Minacce alla posta elettronica

- Attacco all'integrita'
- Attacco all'autenticazione
- Attacco al non ripudio
- Attacco alla riservatezza

## Il protocollo S/MIME

### Servizi offerti

- Firme digitali
- Crittografia dei messaggi

### Protocolli usati

- SHA1
- DSS
- RSA
- 3DES

---

# Sicurezza delle connessioni con SSL/TLS

## Cosa puo' fare?

A livello di sessione puo' permettere:

- Privatezza del collegamento
- Autenticazione
- Affidabilita'

## Quali sono i soggetti coinvolti nel protocollo SET?

- Possessore della carta
- Distributore di carta di credito
- Commerciante
- Acquisitore
- Gateway di pagamento

## Come funziona il pagamento?

- Il possessore invia una richiesta di acquisto
- Il venditore contatta il gateway di pagamento
- Il gateway invia una risposta al venditore
- Il venditore consegna la merce richiesta al possessore della carta

# La difesa tramite Firewall

## Cos'e' il firewall?

Sistema hardware o software dedicato alla difesa e al filtraggio del traffico in entrata e in uscita di una rete.

## Come funziona?

Durante la fase di filtraggio, il firewall fa passare solo tipi di pacchetti che soddisfano determinate regole.

## I tre principi fondamentali

- Il firewall deve essere l'unico punto di contatto della rete interna con quella esterna
- Solo il traffico autorizzato puo' attraversare il firewall
- Il firewall deve essere un sistema altamente sicuro

## Come si classificano i firewall?

#### In base al traffico filtrato

- Ingress
  - Collegamenti in ingresso
- Egress
  - Collegamenti in uscita

#### In base a quanti terminali puo' proteggere

- Personal firewall
  - Protezione di un solo computer
- Network firewall
  - Controlla tutto il traffico della rete

#### Tipo di filtraggio

- Filtro di pacchetti IP
- Server proxy

### Tipi di firewall

- Packet-filtering router
  - Livello di rete
  - 2 tipi di regole
    1. Deny -> Declina con messaggio d'errore
       - Discard/Reject -> Declina senza messaggio d'errore
    2. Permit -> Permetti
  - Vantaggi:
    - Trasparenza
    - Velocita' perche' lavora a basso livello
    - Si deve configurare solo il firewall
  - Svantaggi
    - Vulnerabilita' a:
      - Attacchi di alto livello
      - Mancanza di servizi aggiuntivi
      - IP Spoofing
      - Source routing
      - Attacchi a frammenti piccoli
- Stateful inspection firewally
  - Crea una tabella per ogni connessione attiva
  - Traffico controllato solo all'inizio della connessione
- Circuit gateway
- Proxy server

Nelle aziende alcuni vengono combinati per una maggiore efficienza.

# Reti wireless

## Principali benefici

- Mobilita'
- Connettivita' a breve termine
- Installazione dove il cablaggio puo' essere difficoltoso

## Tipi di reti wireless

- Reti radiomobili -> Connessione dati
  - Tante reti sul territorio
    - Determinate aree
  - 3 Funzionalita'
    - Localizzazione
    - Registrazione -> Identificazione e autenticazione
    - Handover -> passaggio da una cella all'altra
- WLAN -> Rete locale Wireless
  - Standard 802.11x, dove x puo' essere una lettera da 'A' a 'N'
- BAN -> Body Area Network
  - Tutte le reti che indossiamo
    - Smartwatch

## Su quanti canali su puo' trasmettere?

- 13 Canali
  - La velocita' cambia a seconda dell'area e a seconda della distanza dall'access point

## Protocolli wireless

Il protocollo base e' 802.11, ma ve ne sono diversi

- 802.11b
  - Prima versione
- 802.11a
  - Velocita' massima 54 mbps
- 802.11g
  - Alcuni miglioramenti
- 802.11i
  - Maggiore velocita'
  - Maggiore sicurezza
- 802.11ac
  - Diverse modalita' di trasmissione

### Da quante parti e' formato il frame 802.1x?

3 parti

# Crittografia e configurazione nelle reti wireless

Si deve garantire:

- Integrita' dei dati
- Autenticazione

## Tipologie di attacchi

- Eavesdropping
  - Ascolto dei pacchetti, ed eventuali modifiche
- Accessi non autorizzati
- Danni materiali
  - Danni all'hardware

## Tipologie di crittografia di dati

- WEP
  - A chiave simmetrica
  - Chiave di sessione
  - Debole
- WPA
  - Piu' sicuro
  - Basato su 802.1X -> server RADIUS
  - WPA/PSK -> PSK = Passphrase -> password

## Come funziona un server RADIUS?

- Client entra nel raggio d'azione dell'access point
- Client si identifica
- Il server radius richiede altre credenziali
- Il client invia le proprie credenziali
- Il server RADIUS verifica le credenziali
- Il server manda una chiave all'access point
- L'access point trasmette la chiave al client

## Tecnologie trasmissive

- Tecnologie radio
  - 2.4 GHz
  - 5 GHz
  - Sistema che evita le collisioni
  - Attenuate dai materiali
    - Legno -> Attenuazione debole
    - Matton -> Attenuazione media
    - Metallo -> Attenuazione molto alta
  - Attenuate da altre sorgenti
  - Scattering -> onde **ritardate**
- Tecnologie ottiche

# Applicazioni distribuite

## Da quante parti sono formate?

- Front-end -> livello presentazione
- Mid-end -> logica applicativa
- Back-end -> logica di accesso

## In quanti livelli possiamo distinguerle?

- Single tiered
- Two tiered
- Three tiered

[Per approfondire](../Tepsit/Tepsit5A.md#architettura-a-strati)

## Cosa sono le server farm?

Luoghi dove vengono installati un insieme di server.

Possono essere di due tipi:

- Cloning
  - Stesse applicazioni e programmi su tutte le macchine
  - Sistema di load-balancing
    - Divide il lavoro tra tutte la macchine
  - RACS -> Servizi clonati affidabili
    - Shared nothing
    - Shared disk
- Partitioning
  - Ogni macchina svolge un compito diverso

Questi due tipi di server possono essere usati assieme.

## Livelli di sito

1. Read-only
2. Interazione base col sito (Download di file dal sito)
3. Interazione maggiore (Download e upload dal sito)
4. Transazioni online

## Modalita' di accesso ai siti

- Sito internet
- Sito intranet
  - Accesso solo alle aziende
- Sito extranet
  - Accesso alla rete da parte di altri utenti

# Architettura dei sistemi web

Composta da:

- Web server
- Script engine
- Application server
- DBMS server

Zona DMZ = Zona demilitarizzata, il confine tra la rete interna e quella esterna

[Per approfondire](../Tepsit/Tepsit5A.md#client-server)

# Amministrazione di una rete

## Installazione dei componenti software

- Scelta del sistema operativo
- Configurazione dei protocolli di rete

## Autenticazione del client

- User to host
  - Host autentica gli utenti
- Host to host
  - Host autentica altri host
- User to user
  - User autentica e si accerta che l'altro sia effettivamente chi dice di essere

### Tecniche usate

- Something you are
  - Qualcosa che sei -> Autenticazione biometrica
- Something you know
  - Qualcosa che sai -> Password
- Something you have
  - Qualcosa che hai -> token / chiave d'accesso fisica

## Servizi di directory

Metodi per organizzare gli utenti in gruppi, dove solo un determinato gruppo puo' accede ad una determinata directory

# DNS

Servizio di directory che riguarda la trasformazione degli hostname in indirizzi IP

# I domini

Permessi e diritti differenti per un determinato gruppo di utenti

## Albero di domini

Gerarchia di domini

# Active directory

## Cos'e'?

Un database integrato per la serie Windows Server

## A cosa serve?

Serve a controllare e definire le autorizzazioni di accesso degli utenti e delle risorse

## Cosa sono i criteri di gruppo?

I criteri di gruppo consentono agli amministratori di sistema di definire e controllare le impostazioni dei computer e degli utenti in modo centralizzato, rendendo più facile la gestione di grandi gruppi di computer in una rete.
