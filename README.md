# pm-template-listener

Standalone Redis listener template for `trades.raw`.

## Docker

```bash
docker build -t pm-template-listener .
docker run --rm \
  --add-host=host.docker.internal:host-gateway \
  -e REDIS_URL=redis://host.docker.internal:6379/0 \
  pm-template-listener
```

## Local run

No venv is needed if you use Docker. If you want to run it directly, create one and install `redis`:

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install redis
python main.py
```

Environment variables:

- `REDIS_URL` — defaults to `redis://localhost:6379/0`
- `CHANNEL` — defaults to `trades.raw`
- `MIN_USDC` — defaults to `0.0`

