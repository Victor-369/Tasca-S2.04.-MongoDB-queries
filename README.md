# Task S2.04 – MongoDB Queries

A collection of 32 MongoDB queries run against `restaurants` sample dataset.

## Contents

| File | Description |
|------|-------------|
| `docker-compose.yml` | Spins up a local MongoDB 8.0 instance for development. |
| `queries.js` | The 32 exercise queries, each preceded by a comment describing what it does (comments in Catalan). |
| `LICENSE` | Project licence. |

## Requirements

- [Docker](https://docs.docker.com/get-docker/) and Docker Compose
- The `restaurants` dataset in JSON format
- Optionally, [MongoDB Compass](https://www.mongodb.com/products/compass) or `mongosh` for running the queries

## Getting started

### 1. Start MongoDB

```bash
docker compose up -d
```

This starts a container called `mongodb-dev` listening on port `27017`, with data persisted in named volumes. The default credentials can be overridden with environment variables (for example, in a `.env` file):

| Variable | Default |
|----------|---------|
| `MONGO_ROOT_USER` | `admin` |
| `MONGO_ROOT_PASSWORD` | `dev_password_123` |

The default credentials are intended for local development only.

### 2. Import the dataset

Copy the JSON file into the container and import it into the `practicas` database:

```bash
docker cp restaurants.json mongodb-dev:/tmp/restaurants.json
docker exec -it mongodb-dev mongoimport \
  --username admin --password dev_password_123 --authenticationDatabase admin \
  --db practicas --collection restaurants --file /tmp/restaurants.json
```

Add `--jsonArray` if the file contains a single JSON array rather than one document per line.

### 3. Run the queries

Open a shell inside the container:

```bash
docker exec -it mongodb-dev mongosh -u admin -p dev_password_123 --authenticationDatabase admin practicas
```

Then paste the queries from `queries.js` one at a time. Alternatively, connect with MongoDB Compass using:

```
mongodb://admin:dev_password_123@localhost:27017/?authSource=admin
```

## Queries overview

| # | Topic |
|---|-------|
| 1–4 | Basic `find` and field projection |
| 5–7 | Filtering by borough, with `limit` and `skip` |
| 8–12 | Numeric comparisons on scores and coordinates, `$elemMatch`, implicit vs explicit `$and` |
| 13 | Combined filters with sorting |
| 14–16 | Pattern matching with `$regex` (starts with, ends with, contains) |
| 17–19 | Set membership with `$in` and `$nin` |
| 20–21 | Score thresholds and combined `$and` / `$or` logic |
| 22–23 | Matching array elements, including by position (`grades.1`) |
| 24 | Geospatial search with a `2dsphere` index and `$near` |
| 25–27 | Sorting on one or more fields |
| 28–29 | Field existence (`$exists`) and BSON type checks (`$type`) |
| 30 | Modulo filtering with `$mod` |
| 31–32 | Case-insensitive regex and score ranges |

## Stopping the environment

```bash
docker compose down        # stop the container, keep the data
docker compose down -v     # stop the container and delete the volumes
```

## Licence

Distributed under the terms set out in the [LICENSE](LICENSE) file.
