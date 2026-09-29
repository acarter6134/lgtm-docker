# lgtm-docker

This docker-compose provisions a monitoring and observability environment that can consume and display Prometheus and OpenTelemetry data. This configuration is not immediately suitable for a production environment.

## Starting the Containers

```bash
cd lgtm-docker
docker compose up -d
```

## Sending OLTP Metrics

```bash
# send metrics to Prometheus
telemetrygen metrics --duration inf --otlp-endpoint localhost:4317 --otlp-insecure

# send logs to Loki
telemetrygen logs --duration inf --otlp-endpoint localhost:4317 --otlp-insecure

# send traces to Tempo
telemetrygen traces --duration inf --otlp-endpoint localhost:4317 --otlp-insecure
```

## Accessing Endpoints

| Endpoint          | Port  |
|-------------------|-------|
| Grafana Dashboard | 3000  |
| OLTP gRPC         | 4317  |
| OLTP HTTP         | 4318  |
| Prometheus        | 9090  |
| Alloy Dashboard   | 12345 |
