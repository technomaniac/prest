# pREST
[![Build Status](https://travis-ci.org/nuveo/prest.svg?branch=master)](https://travis-ci.org/nuveo/prest)

Serve a RESTful API from any PostgreSQL database

## Problem
There is the PostgREST written in haskell, keep a haskell software in production is not easy job, with this need that was born the pREST.

## Install

    go install github.com/nuveo/prest

## Run

Params:

- PREST\_HTTP_PORT (default 3000)
- PREST\_PG_HOST (default 127.0.0.1)
- PREST\_PG_USER
- PREST\_PG_PASS
- PREST\_PG_DATABASE
- PREST\_JWT_KEY

```
PREST_PG_USER=postgres PREST_PG_DATABASE=prest PREST_HTTP_PORT=3010 prest # Binary installed
```


## API`s
HEADER:

```
Authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiYWRtaW4iOnRydWV9.TJVA95OrM7E2cBab30RMHrHDcEfxjoYZgeFONFh7HgQ
```

### Select - GET

```
http://127.0.0.1:8000/databases (show all databases)
http://127.0.0.1:8000/schemas (show all schemas)
http://127.0.0.1:8000/tables (show all tables)
http://127.0.0.1:8000/DATABASE/SCHEMA (show all tables, find by schema)
http://127.0.0.1:8000/DATABASE/SCHEMA/TABLE (show all rows, find by database and table)
http://127.0.0.1:8000/DATABASE/SCHEMA/TABLE?_page=2&_page_size=10 (pagination, page_size 10 by default)
http://127.0.0.1:8000/DATABASE/SCHEMA/TABLE?FIELD=VALUE (filter)
http://127.0.0.1:8000/DATABASE/SCHEMA/TABLE?_renderer=xml (JSON by default)
```