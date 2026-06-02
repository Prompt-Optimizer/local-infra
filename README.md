# local-infra

Docker Compose setup for local development infrastructure. Provisions all shared dependencies for the prompt-optimizer platform.

## Services

| Service | Image | Ports | Purpose |
|---|---|---|---|
| `optimization-rabbitmq` | RabbitMQ 4 | `5672`, `15672` | Optimization pipeline broker |
| `shared-rabbitmq` | RabbitMQ 4 | `5673`, `15673` | Auth + notification broker |
| `optimization-mongodb` | MongoDB 8.0 | `27017` | Shared database |

All services are connected via `optimization_network` bridge network.

## Run

```bash
docker compose up -d    # start all
docker compose down     # stop all
docker compose logs -f  # follow logs
```

## RabbitMQ management UIs

- Optimization broker: http://localhost:15672 (admin / password)
- Shared broker: http://localhost:15673 (admin / password)

## MongoDB

- Host: `localhost:27017`
- Credentials: `admin / password`
- Default database: `mongodb`
