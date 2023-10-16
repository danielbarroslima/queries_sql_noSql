Neste arquivo dou um breve exemplo de como fazer a alteração de colunas em tabelas.

```sql
-- Alterar coluna na tabela
ALTER TABLE users MODIFY COLUMN address VARCHAR(70);
```

```sql
-- Adicionar incremento automático em "id" na tabela
ALTER TABLE users
    MODIFY COLUMN id INT NOT NULL AUTO_INCREMENT;
ALTER TABLE users
    MODIFY COLUMN id INT NOT NULL AUTO_INCREMENT;
```


```sql
-- Modificar coluna na tabela
ALTER TABLE reserves
    MODIFY COLUMN id_user INT NOT NULL;
ALTER TABLE reserves
    MODIFY COLUMN id_destination INT NOT NULL;
```

```sql
-- Adicionar chave estrangeira (FK) e cascata na exclusão
ALTER TABLE reserves
    ADD CONSTRAINT fk_reserva_usuario_id
    FOREIGN KEY (id_user)
    REFERENCES users (id)
    ON DELETE CASCADE;
ALTER TABLE reserves
    ADD CONSTRAINT fk_reserva_destino_id
    FOREIGN KEY (id_destination)
    REFERENCES destinations (id)
    ON DELETE CASCADE;
```

```sql
-- Aplicação da 1ª Forma Normal (1FN) no banco de dados
-- Adicionar colunas na tabela
ALTER TABLE users
    ADD street VARCHAR(100),
    ADD number VARCHAR(10),
    ADD referencia VARCHAR(50),
    ADD city VARCHAR(50),
    ADD full_state VARCHAR(20);
```
```sql
-- Copiar dados de uma coluna e adicionar fragmentos em outras colunas
UPDATE users
SET street = SUBSTRING_INDEX(SUBSTRING_INDEX(address, ',', 1), ',', -1),
    number = SUBSTRING_INDEX(SUBSTRING_INDEX(address, ',', 2), ',', -1),
    city = SUBSTRING_INDEX(SUBSTRING_INDEX(address, ',', 3), ',', -1),
    full_state = SUBSTRING_INDEX(address, ',', -1);
```
