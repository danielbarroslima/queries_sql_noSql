Neste arquivo dou um breve exemplo de como usar algumas funções com os dados nas tabelas.


```sql
-- COUNT
SELECT COUNT(*) AS users FROM users us INNER JOIN reserves rs ON rs.id_user = us.id;
```

```sql
-- MAX
SELECT MAX(TIMESTAMPDIFF(YEAR, birth_date, CURRENT_DATE())) AS maior_idade FROM users;
```

```sql
-- GROUP BY
SELECT COUNT(*), id_destination FROM reserves GROUP BY id_destination;
```

```sql
-- ORDER BY
SELECT COUNT(*) AS count_reserves, id_destination FROM reserves ORDER BY id_destination DESC, count_reserves DESC;
```
