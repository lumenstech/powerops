# PowerOps Confluent Demo

PowerOps is a real-time monitoring application for generators, ATS systems, and critical building power infrastructure. It uses Confluent to ingest IoT sensor data through an MQTT Source connector, process it with Flink, and generate live alerts and operational metrics.

## Architecture

HiveMQ MQTT Broker → Confluent MQTT Source Connector → `powerops.raw.telemetry` → Flink SQL → `powerops_alerts_out` / `powerops_metrics_out`

## Business Value

PowerOps helps facility teams detect faults faster, reduce downtime, and build a scalable foundation for predictive maintenance.

## Confluent Components Used

- MQTT Source Connector
- Kafka Topics
- Flink SQL
- Schema Registry
- Stream Lineage

## Topics

- `powerops.raw.telemetry`
- `powerops_alerts_out`
- `powerops_metrics_out`

## Sample MQTT Payload

```json
{
  "device_id": "gen-01",
  "site_id": "site-a",
  "asset_type": "generator",
  "metric": "temperature",
  "value": 104.2,
  "status": "warning",
  "event_ts": "2026-03-17T20:15:00Z"
}
