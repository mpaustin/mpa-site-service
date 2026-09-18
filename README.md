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

This repo declares `heroku-24` in `app.json` and pins Java 8 in `system.properties` so builds do not pick up Heroku-24's newer default JDK unexpectedly.

To update the live app stack, use an account with access to the app:

```sh
heroku stack:set heroku-24 -a mpa-site
```

Then deploy a new build.

## Run

```sh
./mvnw spring-boot:run
```

## Verify

```sh
./mvnw test
```
