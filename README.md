# Let's Go Further
This repository contains my code while working through **[Let's Go Further](https://lets-go-further.alexedwards.net/)** by Alex Edwards.
It explores building a production-ready web application in Go, covering authentication, authorization, middleware, database integrations, and more.

## Running
This project uses **PostgreSQL** as its database.
Ensure that PostgreSQL is installed and set up with a database and user named `greenlight`.
The examples below were tested with PostgreSQL **16.9**.
```sql
CREATE DATABASE greenlight;
CREATE ROLE greenlight WITH LOGIN PASSWORD 'pa55word';
CREATE EXTENSION IF NOT EXISTS citext;
GRANT ALL PRIVILEGES ON DATABASE greenlight TO greenlight;
\c greenlight;
GRANT ALL PRIVILEGES ON SCHEMA public TO greenlight;
ALTER SCHEMA public OWNER TO greenlight;
```
This project uses [migrate](https://github.com/golang-migrate/migrate) to manage database schema changes.
Export the database DSN and apply all migrations.
```bash
export GREENLIGHT_DB_DSN="postgres://greenlight:pa55word@localhost/greenlight?sslmode=disable"
migrate -path=./migrations -database=$GREENLIGHT_DB_DSN up
```
To run the application, execute:
```bash
go run ./cmd/api
```
After the server is running, you can hit these endpoints:
```bash
curl -i http://localhost:4000/v1/healthcheck
curl -i -X POST http://localhost:4000/v1/movies
curl -i http://localhost:4000/v1/movies/123
```

## Contributing
This project is primarily for personal learning.
Suggestions, improvements, or discussions are welcome via issues or pull requests.