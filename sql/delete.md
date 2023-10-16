#### Usuários

```sql
-- delete -- necessário buscar o `ID` do registro antes
DELETE FROM users WHERE email = 'example@example.com';
```

#### Destinos

```sql
-- delete -- necessário buscar o `ID` do registro antes
DELETE FROM destinations WHERE id = ID;
```

#### Reservas

```sql
-- delete -- necessário buscar o `ID` do registro antes
DELETE FROM reservas WHERE status = 'cancelada' AND id = ID;