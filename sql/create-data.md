Neste arquivo dou um breve exemplo de como fazer a criação de tabelas.

Os comandos a seguir:

Tabela de **usuarios**;

```sql
CREATE TABLE users (
    id INT PRIMARY KEY,
    name VARCHAR(255) NOT NULL COMMENT 'nome do usuário',
    email VARCHAR(100) NOT NULL UNIQUE COMMENT 'email do usuário',
    address VARCHAR(255) NOT NULL COMMENT 'endereço do usuário',
    birth_date DATE NOT NULL COMMENT 'data de nascimento do usuário');
```

Tabela de **destinos**;

``` sql
CREATE TABLE destinations (
    id INT PRIMARY KEY,
    name VARCHAR(255) NOT NULL COMMENT 'nome do destino',
    description VARCHAR(100) NOT NULL UNIQUE COMMENT 'descrição do destino');
```

Tabela de **reservas**;

```sql
CREATE TABLE reserves (
    id INT PRIMARY KEY,
    id_user INT COMMENT 'Referencia ao id do usuario que fez a reserva',
    id_destination INT COMMENT 'Referencia ao id do destino da reserva',
    date_reserve DATE NOT NULL COMMENT 'data da reserva',
    status VARCHAR(255) NOT NULL DEFAULT 'pendente' COMMENT 'status da reserva');
```
Geram os dados descritos na tabelas abaixo.

## Tabela de Usuários
| Coluna          | Tipo         | Restrições       | Descrição                     |
| --------------- | ------------ | -----------------|-------------------------------|
| id              | INT          | PRIMARY KEY      | Identificador do usuário      |
| name            | VARCHAR(255) | NOT NULL         | Nome do usuário               |
| email           | VARCHAR(100) | NOT NULL, UNIQUE | Email do usuário              |
| address         | VARCHAR(255) | NOT NULL         | Endereço do usuário           |
| birth_date      | DATE         | NOT NULL         | Data de nascimento do usuário |

## Tabela de Destinos
| Coluna      | Tipo         | Restrições       | Descrição                |
| ------------|--------------| -----------------| ------------------------ |
| id          | INT          | PRIMARY KEY      | Identificador do destino |
| name        | VARCHAR(255) | NOT NULL         | Nome do destino          |
| description | VARCHAR(100) | NOT NULL, UNIQUE | Descrição do destino     |

## Tabela de Reservas
| Coluna         | Tipo         | Restrições                   | Descrição                   |
| ---------------|--------------|------------------------------|-----------------------------|
| id             | INT          | PRIMARY KEY                  | Identificador da reserva    |
| id_user        | INT          |                              | Referência ao id do usuário |
| id_destination | INT          |                              | Referência ao id do destino |
| date_reserve   | DATE         | NOT NULL                     | Data da reserva             |
| status         | VARCHAR(255) | NOT NULL, DEFAULT 'pendente' | Status da reserva           |


### Consultas:

#### Users
```sql
-- Selecionar todos os registros da tabela "users"
SELECT * FROM users;
```

```sql
-- Selecionar apenas o nome e o email dos usuários
SELECT name, email FROM users;
```

```sql
-- Selecionar os usuários que possuem o nome "nome do usuário"
SELECT * FROM users WHERE name = 'nome do usuário';
```

```sql
-- Selecionar os usuários que nasceram antes de uma determinada data
SELECT * FROM users WHERE birth_date < '1990-01-01';
```

```sql
-- Like
SELECT * FROM users WHERE name LIKE '%usuário%';
SELECT * FROM users WHERE name LIKE 'no_e%';
```

#### Destinos
```sql
-- Selecionar todos os registros da tabela "destinations"
SELECT * FROM destinations;
```

#### Reservas
```sql
-- Selecionar todos os registros da tabela "reserves"
SELECT * FROM reserves;
```
### Consultas via CLI para verificar como ficou a tabela.

#### Usuários

```sql
-- detalhes da tabela "users"
desc users;
```
| Field           | Type         | Null | Key | Default | Extra          |
|-----------------|--------------|------|-----|---------|----------------|
| id              | int(11)      | NO   | PRI | NULL    | auto_increment |
| name            | varchar(255) | NO   | MUL | NULL    |                |
| email           | varchar(100) | NO   | UNI | NULL    |                |
| birth_date      | date         | NO   |     | NULL    |                |
| street          | varchar(100) | YES  |     | NULL    |                |
| number          | varchar(10)  | YES  |     | NULL    |                |
| city            | varchar(50)  | YES  |     | NULL    |                |
| full_state      | varchar(20)  | YES  |     | NULL    |                |

#### Destinos
```sql
-- detalhes da tabela "destinations"
desc destinations;
```
| Field       | Type         | Null | Key | Default | Extra          |
|-------------|--------------|------|-----|---------|----------------|
| id          | int(11)      | NO   | PRI | NULL    | auto_increment |
| name        | varchar(255) | NO   |     | NULL    |                |
| description | varchar(100) | NO   | UNI | NULL    |                |

#### Reservas
```sql
-- detalhes da tabela "reserves"
desc reserves;
```
| Field          | Type         | Null | Key | Default  | Extra          |
|----------------|--------------|------|-----|----------|----------------|
| id             | int(11)      | NO   | PRI | NULL     | auto_increment |
| id_user        | int(11)      | NO   | MUL | NULL     |                |
| id_destination | int(11)      | NO   | MUL | NULL     |                |
| date_reserve   | date         | NO   |     | NULL     |                |
| status         | varchar(255) | NO   |     | pendente |                |
