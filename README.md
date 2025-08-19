# Let's Go Further
This repository contains my code while working through **[Let's Go Further](https://lets-go-further.alexedwards.net/)** by Alex Edwards.
It explores building a production-ready web application in Go, covering authentication, authorization, middleware, database integrations, and more.

## Running
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