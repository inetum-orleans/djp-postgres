# djp-postgres

A [ddb](https://inetum-orleans.github.io/docker-devbox-ddb) jsonnet package (**djp**).

## Description

PostgreSQL **djp** package.

## Snippet

- `ddb.yml`

```yaml
cookiecutter:
  templates:
    - template: gh:inetum-orleans/djp-postgres
      extra_context:
        postgres_version: "13"
```

- `docker-compose.yml.jsonnet`

```jsonnet
ddb.Compose(
  ddb.with(import '.docker/postgres/djp.libjsonnet',
  name='db',
  params={
    database: 'xxx', 
    login: 'xxx', 
    password: 'xxx', 
    script: ['/data/ddl.sql', '/data/samples.sql']
  })
)
```

## Parameters

| name  | type | description |
| ------------- | ------------- | ------------- |
| database  | string  | Database name
| login  | string  | Database login
| password  | string  | Database password
| script | string[]  | Script to load (see Initialization scripts section in [Docker Hub](https://hub.docker.com/_/postgres))

## Usage

Please check [jsonnet feature](https://inetum-orleans.github.io/docker-devbox-ddb/features/jsonnet/#ddb-jsonnet-packages-djp)
to understand how to include a **djp** package inside a [ddb](https://inetum-orleans.github.io/docker-devbox-ddb) project.

Looking for other [djp packages](https://github.com/inetum-orleans?q=djp-) ? Check github repositories starting with `djp-`.
