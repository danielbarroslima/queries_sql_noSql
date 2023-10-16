Neste arquivo dou um breve exemplo de como fazer a inserção de dados nas tabelas.

```sql
-- Inserir dados na tabela "users"
INSERT INTO users (id, name, email, address, birth_date)
VALUES (2, 'daniel', 'daniel@daniel.com.br', 'endereço', '2023-01-01');
```

```sql
-- Inserir dados na tabela "destinations"
INSERT INTO destinations (id, name, description)
VALUES (1, 'destino 1', 'descrição 1');
```

```sql
-- Inserir dados na tabela "reserves"
INSERT INTO reserves (id, id_user, id_destination, date_reserve)
VALUES (1, 1, 1, '2023-01-02');
```