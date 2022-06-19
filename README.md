# Prerequisites

1. Docker
2. Docker Compose
3. k6

# Setup

```
$ docker-compose up -d
```

# Usage

Replace `PATH_TO_K6_SCENARIO` with path to your scenario and run:

```
$ K6_STATSD_PUSH_INTERVAL=100ms K6_STATSD_ADDR=localhost:8125 K6_STATSD_ENABLE_TAGS=true k6 run --out statsd PATH_TO_K6_SCENARIO
```

Then open http://localhost:3000 and explore Prometheus metrics starting with `k6_`.

# Note

Tested on GNU/Linux (Ubuntu 22.04) and on macOS Monterey (v12.2.1) only, but should be cross-platform solution. The
only platform-specific thing is `extra_hosts` in `docker-compose.yaml` for Docker on GNU/Linux.
