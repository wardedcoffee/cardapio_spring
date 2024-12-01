API criada seguindo o tutorial da Fernanda Kipper, pode ser visto aqui https://youtu.be/lUVureR5GqI?si=xU11kcHLBhXLnHC4
o Front-end: https://github.com/wardedcoffee/cardapioReact

---
## Dependências / Dependencies

- Java version: 17.0.11
- psql (PostgreSQL) 14.13 (Ubuntu 14.13-1.pgdg24.04+1)
- Apache Maven 3.9.9

---
## Entrar no super usuário do Postgres / Access Postgres superuser

```sh
sudo -u postgres psql
```

```sql
\du

\l
```

---
## Criar o banco de dados / Create the database

```sql
CREATE DATABASE food;
```

---
## Entrar nela / Connect to it

```sql
\c food
```

---
## Criar o usuário generic_user / Create user generic_user

```sql
CREATE USER generic_user WITH PASSWORD 'generic_password'; 
GRANT ALL PRIVILEGES ON DATABASE food TO generic_user;
GRANT ALL PRIVILEGES ON ALL TABLES IN SCHEMA public TO generic_user;
```

---
## Caso de problema no Flyway Backup... / In case of Flyway Backup issue...

## Criar a tabela dentro do sistema de um search por create table está em db/migration / Create the table within the system, a search for create table is in db/migration

```sql
CREATE TABLE foods(
    id SERIAL PRIMARY KEY,
    title TEXT NOT NULL,
    price INTEGER NOT NULL,
    image TEXT
);
```

---
## Para rodar a aplicação direto pelo terminal / To run the application directly from the terminal

```sh
mvn spring-boot:run
```

