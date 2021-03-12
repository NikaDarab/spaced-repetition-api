# Italingo API!

Live app: https://italingo.vercel.app/login

API repo: https://github.com/NikaDarab/spaced-repetition-api

Client repo: https://github.com/NikaDarab/spaced-repetition-client

## Summary

Italingo uses spaced repetition technique to help people memorize words in Italian. The app will display words in the Italian language, and ask you to recall the corresponding word in English.

## Technologies used

React.js and Node.js

## Screenshots

![1](https://user-images.githubusercontent.com/43226446/110991807-b43a6600-833a-11eb-88c7-6ab5692c589b.png)
![2](https://user-images.githubusercontent.com/43226446/110991811-b6042980-833a-11eb-98c6-1c3a52ea71c2.png)
![3](https://user-images.githubusercontent.com/43226446/110991818-b7355680-833a-11eb-9ab5-50bed293bd66.png)
![4](https://user-images.githubusercontent.com/43226446/110991823-b8ff1a00-833a-11eb-9d62-e504dba3a5f1.png)

## Local dev setup

If using user `dunder-mifflin`:

```bash
mv example.env .env
createdb -U dunder-mifflin spaced-repetition
createdb -U dunder-mifflin spaced-repetition-test
```

If your `dunder-mifflin` user has a password be sure to set it in `.env` for all appropriate fields. Or if using a different user, update appropriately.

```bash
npm install
npm run migrate
env MIGRATION_DB_NAME=spaced-repetition-test npm run migrate
```

And `npm test` should work at this point

## Configuring Postgres

For tests involving time to run properly, configure your Postgres database to run in the UTC timezone.

1. Locate the `postgresql.conf` file for your Postgres installation.
   1. E.g. for an OS X, Homebrew install: `/usr/local/var/postgres/postgresql.conf`
   2. E.g. on Windows, _maybe_: `C:\Program Files\PostgreSQL\11.2\data\postgresql.conf`
   3. E.g on Ubuntu 18.04 probably: '/etc/postgresql/10/main/postgresql.conf'
2. Find the `timezone` line and set it to `UTC`:

```conf
# - Locale and Formatting -

datestyle = 'iso, mdy'
#intervalstyle = 'postgres'
timezone = 'UTC'
#timezone_abbreviations = 'Default'     # Select the set of available time zone
```

## Scripts

Start the application `npm start`

Start nodemon for the application `npm run dev`

Run the tests mode `npm test`

Run the migrations up `npm run migrate`

Run the migrations down `npm run migrate -- 0`

Seeding `psql -U dunder_mifflin -d spaced-repetition -f /Users/nikadarab/dev/thinkful/spaced-repetition/spaced-repetition-api/seeds/seed.tables.sql`
