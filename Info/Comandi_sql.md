# Comandi sql

---

**SELECT** "attrib": Selezione attributi  
**FROM** "tabella": Da tabella
**WHERE** "condizioni": Condizioni da cercare

```sql
SELECT * FROM Libri WHERE editore="Hoepli"

SELECT isbn, titolo, autore FROM Libri WHERE editore="Hoepli"
```

---

**ALIAS**: rinomina le tabelle per la query esistente

```sql
SELECT isbn AS codice, titolo, prezzo FROM libri AS L WHERE autore="Camagni Paolo"
```

---

**DISTINCT**: seleziona solo attributi differenti

```sql
SELECT DISTINCT interprete FROM dischi
```

---

**ORDER BY** "ASC/DESC": ordina per ascendente o discendente

```sql
SELECT DISTINCT interprete FROM dischi ORDER BY interprete ASC

SELECT DISTINCT interprete FROM dischi ORDER BY interprete DESC
```

---

**BETWEEN** "valore minimo" **AND** "valore massimo": tra vm e vM

```sql
SELECT P.nome, P.cognome, P.altezza
FROM studenti AS P
WHERE P.altezza BETWEEN 160 AND 170
```

---

**LIKE** "valore stringa da cercare%":

```sql
SELECT S.nome, S.cognome
FROM studenti AS S
WHERE S.cognome LIKE 'R%' OR S.cognome LIKE 'G%'
```

---

**IN** "(valore1, valore2, valore3, ... valoreN)":

```sql
SELECT nome, cognome
FROM pazienti
WHERE provincia IN('CO', 'TO', 'MI');
```

---

**IS NULL**: Controlla se un elemento e' nullo

```sql
SELECT V.data_visita, V.id_paziente, V.pressione_min
FROM visite V
WHERE (V.pressione_min IS NULL OR V.pressione_min < 80)
```

---

---
