# Deploy ParadeDB on Render

This repo can be used to deploy [ParadeDB] on Render.

* It uses the [official ParadeDB Docker image](https://hub.docker.com/r/paradedb/paradedb).

* [Render Disks](https://render.com/docs/disks) provide fast, persistent SSD storage for your database.

* ParadeDB runs in your [private network](https://render.com/docs/private-services) and isn't exposed to the public Internet.

## Deployment

### One Click

Use the button below to deploy ParadeDB on Render.

[![Deploy to Render](http://render.com/images/deploy-to-render-button.svg)](https://render.com/deploy)

### Manual

1. Fork this repo.
2. Create a new **Private Service** on Render.
3. Connect your forked repo and use the `Dockerfile` runtime.
4. Add a **Disk** mounted at `/var/lib/postgresql` with at least 10 GB.
5. Set the following environment variables:
   - `POSTGRES_USER` — database user (e.g. `paradedb`)
   - `POSTGRES_PASSWORD` — a strong password
   - `POSTGRES_DB` — database name (e.g. `paradedb`)

## Connecting

Once deployed, connect from any other service in your Render private network:

```
psql -h paradedb -U paradedb -d paradedb
```

## What is ParadeDB?

ParadeDB is an Elasticsearch alternative built on Postgres. It provides:

* Full-text search with BM25 ranking via `pg_search`
* Hybrid search combining BM25 and vector similarity
* Fast analytics on Postgres with columnar storage via `pg_analytics`

Learn more at [paradedb.com](https://www.paradedb.com/).

[ParadeDB]: https://www.paradedb.com/
