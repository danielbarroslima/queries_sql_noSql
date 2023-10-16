#### Usuários
```sql
-- Update -- necessário buscar o `ID` do registro antes
UPDATE users SET address = 'Nova Rua, 123' WHERE email = 'example@example.com';
```

#### Destinos
```sql
-- Update -- necessário buscar o `ID` do registro antes
UPDATE destinations SET description = 'nova descrição' WHERE description = 'description' AND id = ID;
```

#### Reservas
```sql
-- Update -- necessário buscar o `ID` do registro antes
UPDATE reservas SET status = 'cancelada' WHERE id = ID;
```
