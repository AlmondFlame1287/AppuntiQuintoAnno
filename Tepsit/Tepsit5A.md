# Tepsit per il Quinto Anno

## Programma tepsit quest'anno

---

### Argomenti per il compito:

- [Sistemi distribuiti](Tepsit5A.md#cosa-sono-i-sistemi-distribuiti)
- [Modello client-server](Tepsit5A.md#modello-client-server-base)
- [Architettura a strati](Tepsit5A.md#architettura-a-strati)
- [Socket](Tepsit5A.md#socket)

### Parte teorica:

- **Architettura di rete**
- **Sistemi distrubiti**
- [**Modello client-server**](./Tepsit5A.md#modello-client-server-base)
- **Applicazioni di rete**
- [**XML**](./Tepsit5A.md#xml)
- **Android e dispositivi mobili**
- **Socket e comunicazioni con protocollo TCP e UDP**
- [**Servlet**](./Tepsit5A.md#servlet)

### Parte pratica:

- **Applicazioni Java in rete** (Di solito nei PON)

## Modello client-server base

---

Ci sono tanti tipi di server.

Esempio:

- Posta elettronica

- Web

## XML

---

Usato per la descrizione dei dati con dei tag

**Un documento XML che rispetta le regole sintattiche si dice ben formato (well-formed).**

**Un documento XML che rispetta le regole sintattiche e le regole semantiche si dice valido**

## Servlet

---

Sorta di sottoprogrammi che possono andare in parallelo <br>

---

# Architettura di rete

---

## Cosa sono i sistemi distribuiti?

Sono dei sistemi dove le informazioni sono in posizioni geografiche diverse, ma che vengono inserite tutte all'interno di un solo computer.

### Quando si chiama distribuito?

Si chiama distribuito quando:

- Le applicazioni risiedono su piu' host che collaborano tra loro;
- databse distribuito si piu' host

### I benefici del sistema distribuito

- Nel caso in cui venga a mancare uno dei terminali che lo compone, grazie alla **ridondanza**, i dati non verrano persi.
- Un altro vantaggio e' l'**integrazione** tra i diversi pezzi hardware e software che siano. (Nello stesso sistema posso avere sia _Windows_ che _Linux_)
- La **trasparenza**, ovvero non vedere tanti terminali tutti diversi tra loro, ma vederli come un solo singolo sistema.
- **Economicita'**, infatti una **rete di PC** costa meno di un **server**
- **L'apertura**, l'utilizzo da parte di fornitori hardware e software differenti
- **Connettivita' e collaborazione**, ovviamente la condivisione dell'attrezzatura, quali per esempio la classica stampante.
- **Prestazioni e scalabilita'**, ampliamento dell'hardware con effettiva miglioria delle performance

### Svantaggi del sistema distribuito

- **Produzione di software**, per far funzionare all'unisono piu' terminali alla volta, i programmatori si sono dovuti adeguare, pensando in modo diverso. Per farlo, ci sono state 3 tappe:
  - Definizione dello standard TCP/IP;
  - Sviluppo delle architetture Web, sia lato client come HTML, CSS, JS sia sul lato server come PHP;
  - Il diffondersi del linguaggio Java, grazie alla JVM ha potuto permettersi l'esecuzione dello stesso programma su piu' piattaforme diverse;
- **Complessita'**
- **Sicurezza**
- **Comunicazione**, dovuto alle tecniche di trasporto dei dati.

### La differenza con il sistema parallelo

I sistemi parallelo e' un insieme di elementi che comunicano e cooperano per risolvere un problema in meno tempo possibile, mentre i sistemi distributi **possono** ma non devono per forza cooperare con altri terminali;

## Client-server

---

Il **client** e' un terminale che ha la funzione di cliente;

Il **server** e' un terminale che ha la funzione di servente, praticamente fornisce dei servizi;

L'**Actor** e' un terminale che ha le funzioni di ambo le parti.

La comunicazioni in questo modello avviene tramite [Socket](./Tepsit5A.md#socket), formato da **"Indirizzo IP:Numero della porta"**

## Cluster di PC

---

I calcolatori lavorano in parallelo per ottenere una gran potenza di calcolo senza aver bisogno di spendere troppo.

- **Cluster**: macchine uguali
- **Grid**: macchine differenti

Struemnto per creazione Cluster: **ParallelKnoppix**

## Architettura WEB-centric

---

Sistema distribuito gestito tramite il web

## Middleware

---

**!!IMPORTANTE!!**<br>

E' un software che si pone come livello intermedio che si pone tra applicazioni e sistema operativo, che gestice alcune operazioni.

### Servizi

Fornitura di qualche tipo di dato

## Modello object-based

---

Ogni risorsa viene vista come oggetto, dunque vi e' un gestore che le distribuisce. Questo tipo di modello e' completamente distribuito.

## Architettura a strati

---

Suddivisa in:

- **Front-end** - GUI per l'utente (Presentation Layer) / Client
- **Middle tier** - Elaborazione (Resource Managment Layer) / Middleware
- **Back-end** - Accesso ai dati/risorse (Business Logic Layer) / Server

### Architettura a 1 livello

Un computer con un solo utente e una sola applicazione aperta;

### Architettura a 2 livelli

Architettura simile client-server. Due modi di implementazione:

- #### Thick-client

  Livello di presentazione ed elaborazione a carico del client, lato di accesso ai dati rimane sul server

- #### Thin-client
  Livello di presentazione a carico del client, lato di elaborazione e accesso sul server

## Socket

---

Un socket consente di comunicare attraverso la rete utilizzando il TCP/IP, ed e' quindi parte integrante del protocollo.

### Socket di benvenuto

Socket in attesa di nuove connessioni; trasferisce la richiesta su un socket di connessione

### Socket di connessione

Socket che gestisce la connessione dal suo inizio al suo decesso;

## Concetto di socket

Il concetto di socket e' stato sviluppato sulla base di I/O sul file. Ogni sistema operativo mette a disposizione delle proprie API per la connessione tra due socket.

## Famiglie di socket

Ogni famiglia ha una serie di stili di comunicazione differenti:

- Internet socket: permette il trasferimento dati tra processi posti su macchine remote
- Unix Domain Socket: permette il trasferimento di dati tra processi sulla stessa macchina Unix

## Tipi di socket

A seconda di come sono organizzati i socket abbiamo 3 tipi di socket:

- [Stream socket](Tepsit5A.md/#stream-socket)
- [Datagram socket](Tepsit5A.md/#datagram-socket)
- Raw socket

### Stream socket

Basato su un flusso di byte in entrata. Funziona in questo modo:

1. Il server si mette in ascolto in attesa di collegamento
2. Il client si pone in coda sul socket del server, e quando viene accettato, il server inizia la trasmissione dati
3. Alla creazione della trasmissione, la porta della connessione viene spostata dalla porta ricevente

Un esempio molto largo di questo tipo di socket e' il [**Protocollo TCP**](../Sistemi/Sistemi4A.md#tcp)

### Datagram socket

Flusso di byte che non garantisce l'ordine di arrivo dei pacchetti, quindi basato su [Protocollo UDP](../Sistemi/Sistemi.md#udp)

## Per cosa viene utilizzato il multicast?

Il **multicast** serve per trasmettere informazioni a piu' macchine, e per farlo, si usa un indirizzo IP di **classe D** che successivamente viene convertito in un indirizzo normale (classe A, B, C).

# Comunicazione dinamica con le pagine web

---

## Cos'e'?

## Come vengono classificate?

- Tramite URL
  - [CGI](./Tepsit5A.md#cgi) (Common Gateway Interface)
  - [Java servlet](./Tepsit5A.md#servlet)
  - NSAPI
- Tramite codice in HTML
  - SSI-Apache
  - ASP-Microsoft
  - PHP
  - Java Server Pages (JSP)

### CGI

Script eseguiti dal sistema operativo del server. Eseguito solo in risposta alla chiamata. Nel caso in cui esso venisse eseguito piu' volte, dovra' essere ricaricato in memoria. Aumenta il tempo di latenza.

## Servlet

Script eseguiti dalla JVM. Al contrario delle CGI, il Servelt viene caricato in memoria, e rimane li' ad attendere una richiesta.

### Cosa sono?

Sono delle componenti scritti in Java che producono contenuto web dinamico, ovvero contenuto dove noi possiamo interagire.

### Gestione delle richieste

Dato che il container, ovvero l'ambiente di esecuzione delle servlet, si occupa della gestione delle suddette, questo fa si che lo sviluppatore si possa concentrare sullo sviluppo logico delle applicazioni web.

### Flusso di esecuzione

- Client invia una richiesta
- Se si tratta di prima richiesta, allora si istanzia e si carica il servlet
- Si attiva il thread che gestisce la comunicazione tra client e server
- Il server invia al thread-serverlet la richiesta pervenutagli dal client
- Il thread-serverlet costruisce la riposta e la inoltra al server
- Il server invia la risposta al client

# Database

Per una spiegazione migliore [clicca qui](../Info/Database.md#database)

## JDBC

Driver per la connessione ai DB in Java.
Le chiamate vengono tradotte in ODBC prima di essere eseguite

## API native

Le API native invece, al contrario del driver JDBC, sono usate per le chiamate che non vengono tradotte in ODBC.

## Database embedded

## Cosa sono?

Database snelli, strettamente legati alle applicazioni. <br>
Un esempio di questi puo' essere **SQLite** (usato per whatsapp e altre app di messaggistica)
