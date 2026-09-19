# MPA Site Service

Small Spring Boot service for the `mpa-site` Heroku app.

## Requirements

- Java 8+
- Maven wrapper included in this repo
- PostgreSQL database

## Configuration

Set these environment variables in Heroku or your local shell:

- `DATABASE_URL` JDBC URL for PostgreSQL, for example `jdbc:postgresql://localhost:5432/mpa_site`
- `DATABASE_USERNAME` database username
- `DATABASE_PASSWORD` database password
- `HIBERNATE_SHOW_SQL` optional, defaults to `false`

## Heroku

This repo declares `heroku-26` in `app.json` and pins Java 8 in `system.properties` so builds do not pick up Heroku-26's newer default JDK unexpectedly.

To update the live app stack in the Heroku UI, choose the `heroku-26` stack for `mpa-site`, then deploy a new build. The CLI equivalent is:

```sh
heroku stack:set heroku-26 -a mpa-site
```

## Run

```sh
./mvnw spring-boot:run
```

## Verify

```sh
./mvnw test
```
