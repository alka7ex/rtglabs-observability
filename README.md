# Deployment Stack: 3 Go Apps + Grafana Alloy

## 🧱 Services

- `alloy`: OpenTelemetry collector (OTLP, sends to Grafana Cloud)

## 📦 Usage with Coolify

1. Clone this repo into a new GitHub repository.
2. In Coolify:

   - Create a new **Docker Compose app**
   - Point it to this repo
   - Add an environment variable: `GRAFANA_CLOUD_API_KEY`

3. Coolify will build and start all containers.
4. Your Go apps will send traces/metrics/logs to Alloy.
5. Alloy will forward them to Grafana Cloud.

## 🌐 Ports

| Service           | Port |
| ----------------- | ---- |
| alloy (OTLP gRPC) | 4317 |
| alloy (OTLP HTTP) | 4318 |

## 📝 Notes

- Modify `docker-compose.yml` to point to your real container image URLs.
- Add more services (e.g. Redis, Postgres) if needed.
