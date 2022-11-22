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

## Crittografia

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
