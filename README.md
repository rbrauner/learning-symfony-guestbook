# learning-symfony-guestbook

## Development run

`docker compose -f ./docker-compose.dev.yml up --build -d`

## Production build

Set `DOCKER_IMAGE_TAG` variable in `.env` to `latest` or version e.x. `v1.0.0` and run:

- `docker compose -f ./docker-compose.build.yml build`
- `docker compose -f ./docker-compose.build.yml push`

## Production deploy

Copy `.env` and `docker-compose.prod.yml` to production, adjust `.env` and run:

- `docker compose -f ./docker-compose.prod.yml pull`
- `docker compose -f ./docker-compose.prod.yml up -d`
