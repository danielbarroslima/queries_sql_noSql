Neste arquivo dou um breve exemplo de como fazer consultas com subconsultas em tabelas.

```sql
-- Subconsulta
SELECT name,
  (SELECT COUNT(*) FROM reserves WHERE id_user = 1) AS total_reserves
  FROM users;
```

onde olhamos assim:

```sql
-- Consulta para obter o nome dos usuários e o resultado de uma subconsulta
SELECT name,     <!--- o que queremos da consulta --->
  (SELECT COUNT(*) FROM reserves WHERE id_user = 1) AS total_reserves  <!--- subconsulta --->
FROM users;      <!--- onde iremos consultar consulta --->
