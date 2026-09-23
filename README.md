# Express Apollo GraphQL API

A minimal GraphQL API server demonstrating Express integrated with Apollo Server, with a pluggable database layer supporting MongoDB or SQL Server.

## What's inside

- Express server (`app.js`) wired up with `cookie-parser` and `body-parser`
- Apollo Server mounted on Express via `apollo-server-express`, exposing a GraphQL endpoint with a `hello` query and a `Book` type definition
- A REST route (`GET /api/v1/users`) alongside the GraphQL endpoint
- A database module (`db/index.js`) that can connect to either MongoDB (via Mongoose) or SQL Server (via `mssql`), selected by a driver name passed to `connect()`; the app currently connects using the `mongodb` driver
- Example config file (`config/index.example`) with connection strings for both drivers

## Tech stack

- Node.js, Express
- Apollo Server, GraphQL
- Mongoose (MongoDB) / mssql (SQL Server)

## Quickstart

```bash
bun install
cp config/index.example config/index.js   # edit connection strings as needed
bun run start
```

Or, to auto-restart on source changes (requires `nodemon`):

```bash
bun run watch
```

The server listens on port 3000 by default (override with the `PORT` environment variable).

## Endpoints

- `POST/GET /graphql` - GraphQL endpoint and playground (Apollo Server)
- `GET /api/v1/users` - REST route returning a static list of users

## Project structure

```
app.js            # Express app setup, middleware, DB connect
bin/www           # HTTP server bootstrap
config/           # DB connection config (copy from index.example)
db/               # Database connection module (MongoDB / SQL Server)
graphql/          # Apollo Server instance, schema, type definitions
routes/           # REST routes
```
