# Arteze Shop e-Commerce Backend

The Arteze shop uses a self-hosted [Saleor](https://saleor.io/) instance for it's e-commerce backend core and admin dashboard.

This repo is a clone of [saleor-platform](https://github.com/saleor/saleor-platform) but also consists instructions and env examples for production.

For more info on how Saleor works you can read their documentation - [saleor docs](https://docs.saleor.io/)
## Local Development

1. Start up docker desktop and docker compose
2. Go to the directory:
```shell
cd backend
```

3. Apply Django migrations:
```shell
docker compose run --rm api python3 manage.py migrate
```

4. Populate the database with example data and create the admin user:
```shell
docker compose run --rm api python3 manage.py populatedb --createsuperuser
```
*Note that `--createsuperuser` argument creates an admin account for `admin@example.com` with the password set to `admin`.*

5. Run the application:
```shell
docker compose up -d
```

### Where is the application running?

- Saleor Core (API) - http://localhost:8000
- Saleor Dashboard - http://localhost:9000
- Jaeger UI (APM) - http://localhost:16686
- Mailpit (Test email interface) - http://localhost:8025
