Neste arquivo dou um breve exemplo de como fazer consultas usando JOIN nas tabelas.

```sql
-- INNER JOIN: Usuários existem, reservas existem
SELECT *
FROM users us
INNER JOIN reserves rs ON us.id = rs.id_user
INNER JOIN destinations ds ON rs.id_destination = ds.id;
```

```sql
-- LEFT JOIN: Usuários existem, reservas não existem
SELECT *
FROM users us
LEFT JOIN reserves rs ON us.id = rs.id_user
INNER JOIN destinations ds ON rs.id_destination = ds.id;
```

```sql
-- RIGHT JOIN: Usuários não existem, reservas existem
SELECT *
FROM users us
RIGHT JOIN reserves rs ON us.id = rs.id_user
INNER JOIN destinations ds ON rs.id_destination = ds.id;
```

```sql
-- FULL JOIN: Usuários não existem, reservas não existem
SELECT *
FROM users us
FULL JOIN reserves rs ON us.id = rs.id_user
INNER JOIN destinations ds ON rs.id_destination = ds.id;
```
