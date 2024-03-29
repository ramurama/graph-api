## Graph Database Prototype

Task description:

Goal: To create a backend application using NestJS and GraphDB. Drivine should be used as a database client. Instagram data schema has to be used. Data can be fetched from Instagram web API and persisted in the graph database using Drivine. Endpoints has to be exposed to query any of the available data from the graph database.

Outcome:

A backend app connected to a drivin supported graph database with a query-interface (no fancy UI necessary - plain REST to curl is fine) return some persisted instagram data

Tools which could be helpful:

- Drivine starter repo (Nestjs, Typescript) (https://github.com/liberation-data/drivine-inspiration)

- Open Source Database Schemas (OSDS) Instagram (https://github.com/Vheissu/Open-Source-Database-Schemas/blob/master/vheissu-instagram-schema.md)

- instagram-web-api (https://github.com/jlobos/instagram-web-api) and instagram-private-api (https://github.com/dilame/instagram-private-api) to get real data from instagram

## Installation

```bash
$ npm install
```

## Prerequisites

Before running the application you need to download and install Neo4J community server or Neo4J Desktop (preferred). Create a database and update the entries in the .env file (Like passsword, database name/passsword. Usually database name would be 'neo4j').

Start the database in the Neo4J project view.

## Environment Variables

- Rename the .env.sample file to .env
- Update the database name/password if you have any.
- Update the following entries.

```bash
INSTAGRAM_USERNAME=<YOUR-INSTAGRAM-USERNAME>
INSTAGRAM_PASSWORD=<YOUR-INSTAGRAM-PASSWORD>

```

## Testing the app

````bash
# development
$ npm run test:e2e
````


## Running the app

```bash
# development
$ npm run start

````

## Endpoints

Execute the following endpoints sequentially in order to fetch data using Instagram API and save it to database before viewing it.

```bash
# fetch and save user to the local database
http://localhost:3000/instagram/user/<IMSTAGRAM-USERNAME>
```

```bash
# get all users from local database
http://localhost:3000/local/users
```

Note: INSTAGRAM-USERID is exactly the same value as the id field from the previous endpoint.

```bash
# fetch and save followers of the user to the local database
http://localhost:3000/instagram/follows/<INSTAGRAM-USERID>
```

```bash
# fetch followers of the user from the local database
http://localhost:3000/local/follows/<INSTAGRAM-USERID>
```

Other endpoints:

```bash
# get one user from local database
http://localhost:3000/local/users/<IMSTAGRAM-USERNAME>
```
