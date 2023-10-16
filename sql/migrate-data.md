Neste arquivo dou um breve exemplo de como fazer a migração de dados entre tabelas.


#### Criação de nova tabela
```sql
CREATE TABLE new_users (
    id INT PRIMARY KEY,
    name VARCHAR(255) NOT NULL COMMENT 'nome do usuário',
    email VARCHAR(120) NOT NULL UNIQUE COMMENT 'email do usuário',
    address VARCHAR(200) NOT NULL COMMENT 'endereço do usuário',
    birth_date DATE NOT NULL COMMENT 'data de nascimento do usuário');

```

#### Inserção de Dados
```sql
INSERT INTO new_users (id, name, email, address, birth_date)
SELECT id, name, email, address, birth_date
FROM users;
```

Definição de como ficará a nova tabela.

### Tabela de Usuários Nova
| Coluna           | Tipo         | Restrições                  | Descrição                        |
|------------------|--------------|-----------------------------|----------------------------------|
| id               | INT          | PRIMARY KEY                | Identificador do usuário         |
| name             | VARCHAR(255) | NOT NULL                   | Nome do usuário                  |
| email            | VARCHAR(120) | NOT NULL, UNIQUE           | Email do usuário                 |
| address          | VARCHAR(200) | NOT NULL                   | Endereço do usuário              |
| birth_date  | DATE         | NOT NULL                   | Data de nascimento do usuário    |
