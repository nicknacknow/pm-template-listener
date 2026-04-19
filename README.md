# pm-template-listener

Standalone Redis listener template for `trades.raw`.

## Runtime

- `REDIS_URL` — Redis pub/sub endpoint, defaults to `redis://localhost:6379/0`
- `CHANNEL` — Redis channel, defaults to `trades.raw`
- `MIN_USDC` — minimum trade size to print, defaults to `0.0`

## Docker

```bash
docker build -t pm-template-listener .
docker run --rm \
  --add-host=host.docker.internal:host-gateway \
  -e REDIS_URL=redis://host.docker.internal:6379/0 \
  pm-template-listener
```

The listener prints formatted trades to stdout and is meant to be copied or adapted.
