# Tepsit per il Quinto Anno

## Programma tepsit quest'anno

---

Parte teorica:

- **Architettura di rete**
- **Sistemi distrubiti**
- [**Modello client-server**](./Tepsit5A.md#modello-client-server-base)
- **Applicazioni di rete**
- [**XML**](./Tepsit5A.md#xml)
- **Android e dispositivi mobili**
- **Socket e comunicazioni con protocollo TCP e UDP**
- [**Servlet**](./Tepsit5A.md#servlet)

Parte pratica:

- **Applicazioni Java in rete** (Di solito nei PON)

## Modello client-server base

---

Ci sono tanti tipi di server.

Esempio:

- Posta elettronica

- Web

[**Per la spiegazione completa**](./Tepsit5A.md#client-server)

## XML

---

Usato per la descrizione dei dati con dei tag <br>
[**Per la spiegazione completa**](./XML.md)

## Servlet

---

Sorta di sottoprogrammi che possono andare in parallelo <br>
[**Per la spiegazione completa**](./Servelet.md)

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
