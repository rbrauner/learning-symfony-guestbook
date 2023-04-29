# learning-symfony-guestbook

## Development run

`docker compose -f ./docker-compose.dev.yml up --build -d`

## Production deploy

Copy `.env` and `docker-compose.prod.yml` to production, adjust `.env` and run:

- `docker compose -f ./docker-compose.prod.yml pull`
- `docker compose -f ./docker-compose.prod.yml up -d`
