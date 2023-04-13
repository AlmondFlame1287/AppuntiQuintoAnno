# Table join

```sql
-- Elenco nome, cognome dei pazienti per i quali e' stata rilevato il valore della glicemia superiore a 100
SELECT V.ID_paziente, V.data_visita, V.peso, V.glicemia, P.cognome, P.nome
FROM visite as V, pazienti as P
WHERE V.ID_paziente = P.id_paziente AND V.glicemia > 100
```
