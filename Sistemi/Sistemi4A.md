# Sistemi Quarto anno

---

## Servizio e funzioni dello stato di trasporto

Si colloca al livello 4 della pila ISO-OSI.
I due protocolli principali sono TCP e UDP

Il [**TCP**](Sistemi.md#tcp) e' un protocollo affidabile, e se non riesce ad inviare e/o a ricevere un pacchetto, esso viene segnalato

L ['**UDP**](Sistemi.md#udp) e' un protocollo non affidabile, ma piu' veloce, di solito usato nello streaming video

## TCP

---

Per realizzare una connessione affidabile si usa un parametro ACK e un tempo limite di risposta RTO (di solito una media tra tutti i tempi di connessione ad un server).

L'**RTO** e' un valore variabile, in quanto se il valore e' troppo piccolo, non si ha il tempo di ricevere i dati, invece se troppo lungo, i dati potrebbero metterci troppo per arrivare.

I segmenti (i pacchetti nell'UDP), sono numerati con **SN** (Sequence Number) e i segmenti ACK sono numerati con **ACKn**

La conferma dell'arrivo dei pacchetti e' fatto in modo cumulativo cioe' di piu' pacchetti consecutivi alla volta.

**Esempio:** Se vengono inviati 10 pacchetti e l'ACK ha valore 6, quindi riceve solo 6 pacchetti, il protocollo deve reinviare solo gli ultimi 4 pacchetti.

Se per un determinato periodo non vengono mandati pacchetti, il protocollo invia dei pacchetti randomici di Keep-Alive, in modo da mantenere attiva la connessione.

Un segmento TCP e' fatto da:

- Intestazione
  - Porta origine
  - Porta destinazione
  - Numero di sequenza
  - ACK
  - Offset
  - Flag per le informazioni
    - SYN - Connessione stabilita? 1 altrimenti 0
    - FIN - Connessione terminata? 1 altrimenti 0
  - Checksum
  - Riempimento
- Payload - Dati

## UDP

---

Utilizzato soprattutto per le chiamate telefoniche e per lo streaming di video formato da:

- Header - 8 byte
  - Porta sorgente
  - Porta destinazione
  - Lunghezza
  - Checksum
- Payload - Dati

L'UDP ha un sistema di rilevazione degli errori grazie al checksum, ma questo e' quanto, dato che non ha nessuna misura di reinvio dei dati.

## Multiplexing/Demultiplexing

---

Il **multiplexing** e' un metodo usato per trasmettere piu' dati su uno stesso canale.

Il **demultiplexing** e' il metodo inverso al multiplexing

## Le porte dell'IP

---

Per usare il principio di multiplexing, e dunque di fare piu' trasmissioni di dati sullo stesso indirizzo IP, si usano le porte (192.168.1.1:_**3002**_) che vanno da 0 a 65535.

Nel caso in cui un server metta a disposizione la porta 80, non significa che esso possa ospitare solo una connessione, ma bensi' esso indirizzera' la connessione su un'altra porta registrata.

Alcune porte sono speciali:

- 80: HTTP
- 23: TELNET

## Quality Of Service

---

E' un parametro che calcola la qualita' della connessione.

- Ritardo massimo
- Numero di byte trasferiti
- Probabilita' di fallimento del trasferimento
- Priorita' della connessione

## Servizi offribili dal livello 4

---

- Multiplexing
- Gestione connessione
- Rivelazione errori
- Trasferimento affidabile
- Controllo del flusso
- Controllo del traffico sulla rete

**TCP utilizza tutti i servizi mentre l'UDP solo multiplexing e gestione della connessione**

---

### DATI INCERTI

---

TCP:

Ha delle primitive (delle funzioni):

1. Listen
2. Send data
3. Receive DAta
4. T-connect
5. T-Disconnect

e in base al linguaggio usato, si hanno dei diversi metodi.
