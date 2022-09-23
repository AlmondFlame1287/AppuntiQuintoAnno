# Database

---

## Cosa significa progettare un database?

Significa progettare le strutture e la logica in modo che si possa raccogliere i dati di cui l'utente ha bisogno.

**I passi principali sono:**

1. Analisi del problema
   - Capire cosa si deve progettare
2. Progettazione concettuale del database
   - Cosa deve essere immesso nel database
   - Si possono usare due modelli
     - [Modello Entita'-Relazione](./Database.md#modello-entita-relazione)
     - Modello ad Oggetti
3. Progettazione logica del database
   - Come deve essere rappresentato il database
   - Traduzione schema concettuale
   - Ha regole di traduzione ben definite
   - Il piu' diffuso e' quello relazionale([SQL](./Database.md#sql))
4. Progettazione fisica e implementazione
5. Realizzazione delle applicazioni

| Modellazione dei dati     | Modellazione funzionale                |
| ------------------------- | -------------------------------------- |
| Analisi del problema      | Progettazione fisica e implementazione |
| Progettazione concettuale | Realizzazione delle applicazioni       |
| Progettazione logica      |                                        |

## Modello Entita'-relazione

---

Rappresenta in modo grafico le strutture di dati. <br>
Permette di comprendere a tutti la struttura del database.

Viene affiancato da un documento tecnico.

## SQL

---

Consiste in un insieme di tabelle connesse tra loro mediante relazioni.

Lo scopo e' di non duplicare inutilmente le informazioni

## DBMS

---

Software per la creazione e gestione di database e per farlo deve accedere in modo efficiente a grandi quantita' di dati.

I dati devono essere:

- Consistenti
- Sicuri
  - Impedire danni al db
- Segreti
  - Impedire accesso ai dati da parte di utenti non autorizzati
- Integri
