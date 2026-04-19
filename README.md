# pm-template-listener

Redis listener for `trades.raw`.

## Prerequisite

Start [`pminspect`](https://github.com/nicknacknow/pminspect) first. It publishes trades to Redis on `redis://localhost:6379/0`.

## Run

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install redis
REDIS_URL=redis://localhost:6379/0 python main.py
```

Optional environment variables:

- `CHANNEL` — defaults to `trades.raw`
- `MIN_USDC` — defaults to `0.0`

## Docker

```bash
docker build -t pm-template-listener .
docker run --rm \
  --add-host=host.docker.internal:host-gateway \
  -e REDIS_URL=redis://host.docker.internal:6379/0 \
  pm-template-listener
```
