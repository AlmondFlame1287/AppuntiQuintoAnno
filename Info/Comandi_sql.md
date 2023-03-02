# Comandi sql

---

**SELECT** "attrib": Selezione attributi  
**FROM** "tabella": Da tabella
**WHERE** "condizioni": Condizioni da cercare

```sql
SELECT * FROM Libri WHERE editore="Hoepli"

SELECT isbn, titolo, autore FROM Libri WHERE editore="Hoepli"
```

ALIAS: rinomina le tabelle per la query esistente

```sql
SELECT isbn AS codice, titolo, prezzo FROM libri AS L WHERE autore="Camagni Paolo"
```

DISTINCT: seleziona solo attributi differenti

```sql
SELECT DISTINCT interprete FROM dischi
```

ORDER BY "ASC/DESC": ordina per ascendente o discendente

```sql
SELECT DISTINCT interprete FROM dischi ORDER BY interprete ASC

SELECT DISTINCT interprete FROM dischi ORDER BY interprete DESC
```
