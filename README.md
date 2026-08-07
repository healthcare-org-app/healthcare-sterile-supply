# sterile-supply-service

sterile-supply-service — domain: identity

- **Port:** 9203
- **Language:** Python 3.11 + Flask
- **Database:** `identity` (Postgres, table `sterile_supply`)
- **Event bus:** Kafka

## API

| Method    | Path                       |
|-----------|----------------------------|
| GET       | `/api/sterile_supply/`          |
| POST      | `/api/sterile_supply/`          |
| GET       | `/api/sterile_supply/<id>`      |
| PUT/PATCH | `/api/sterile_supply/<id>`      |
| DELETE    | `/api/sterile_supply/<id>`      |
| GET       | `/health`                  |
| GET       | `/ready`                   |

## Events

**Publishes:** (none)
**Subscribes:** (none)

## HTTP peer dependencies

- `equipment-service`
- `audit-log-service`
- `erp-procurement`

## Local dev

```bash
pip install -e ../../libs/py-healthcare-common
pip install -r requirements.txt
cp .env.example .env
(cd ../../infra && docker compose up -d postgres kafka kafka-init)
python -m app.main
```

## Tests

```bash
pytest
```
