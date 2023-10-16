
#### Consulta antes de ter o ídice.

```sql
-- Selecionar os usuários que possuem o nome "nome do usuário"
EXPLAIN SELECT * FROM users WHERE name = 'nome do usuário' ORDER BY email ASC;
```

```sql
CREATE INDEX users_name ON users (name);

```

#### Consulta depois de ter o ídice.
```sql
-- consulta para validar indice antes e depois
-- Selecionar os usuários que possuem o nome "nome do usuário"
EXPLAIN SELECT * FROM users WHERE name = 'nome do usuário' ORDER BY email ASC;
```
