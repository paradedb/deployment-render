<h1 align="center">
  <a href="https://paradedb.com"><img src="https://raw.githubusercontent.com/paradedb/paradedb/main/docs/logo/readme.svg" alt="ParadeDB"></a>
<br>
</h1>

<p align="center">
  <b>Postgres for Search and Analytics — deployed on <a href="https://render.com">Render</a></b>
</p>

<h3 align="center">
  <a href="https://paradedb.com">Website</a> &bull;
  <a href="https://docs.paradedb.com">Docs</a> &bull;
  <a href="https://join.slack.com/t/paradedbcommunity/shared_invite/zt-32abtyjg4-yoYoi~RPh9MSW8tDbl0BQw">Community</a> &bull;
  <a href="https://paradedb.com/blog/">Blog</a> &bull;
  <a href="https://docs.paradedb.com/changelog/">Changelog</a> &bull;
  <a href="https://render.com">Render</a>
</h3>

---

This repo deploys [ParadeDB](https://paradedb.com) on Render with one click.

* Uses the [official ParadeDB Docker image](https://hub.docker.com/r/paradedb/paradedb).
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
   - `POSTGRES_USER` — database user (e.g. `postgres`)
   - `POSTGRES_PASSWORD` — a strong password
   - `POSTGRES_DB` — database name (e.g. `paradedb`)

## Connecting

Once deployed, connect from any other service in your Render private network:

```
psql -h paradedb -U postgres -d paradedb
```

Or add an SSH key to Render, connect to the SSH endpoint, then run:

```
psql -U postgres paradedb
```

## What is ParadeDB?

[ParadeDB](https://paradedb.com) is an Elasticsearch alternative built on Postgres. It delivers elastic-quality full-text search, hybrid search, and faceted search — all in pure SQL, with no separate search infrastructure to manage.

* **BM25 full-text search** with 12+ tokenizers across 20+ languages
* **Hybrid search** combining BM25 and vector similarity
* **Faceted search and boolean queries** for filtering and complex search logic
* **Zero ETL** — installs as a Postgres extension or replicates from managed databases (RDS, Supabase, Neon, etc.)

500K+ Docker pulls · 100K+ extension installs · 8K+ GitHub stars

Learn more at [paradedb.com](https://www.paradedb.com/).
