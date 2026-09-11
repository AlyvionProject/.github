# Alyvion

**Distributed Information Security Platform**

Alyvion is a distributed software platform for monitoring, analyzing and responding to information security events.

The project is designed around endpoint agents, centralized event processing, configuration monitoring, incident management and automated security response.

## Architecture

```text
                         ┌──────────────────┐
                         │     Operator     │
                         │  Web Dashboard   │
                         └────────┬─────────┘
                                  │
                                  ▼
                         ┌──────────────────┐
                         │   Alyvion Core   │
                         │                  │
                         │ Event Collector  │
                         │ Correlation      │
                         │ Detection        │
                         │ ML / Anomaly     │
                         │ Incident Manager │
                         │ Response Manager │
                         └────────┬─────────┘
                                  │
                             PostgreSQL
                                  │
             ┌────────────────────┼────────────────────┐
             │                    │                    │
             ▼                    ▼                    ▼
      Linux Agent          Windows Agent          DB Agent
             │                    │                    │
         journald              Event Log          PostgreSQL
         auditd                Sysmon              MySQL
         auth.log              Processes            MS SQL
```

Agents communicate with Alyvion Core using **gRPC over mutual TLS (mTLS)**.

## Components

| Component     | Technology            | Purpose                           |
| ------------- | --------------------- | --------------------------------- |
| Alyvion Core  | C# / .NET             | Central processing and management |
| Alyvion Agent | Rust                  | Endpoint monitoring and response  |
| Web Console   | ASP.NET Core / Blazor | Administration and visualization  |
| Database      | PostgreSQL            | Persistent storage                |
| ML Engine     | Python / ONNX         | Anomaly detection                 |
| Protocol      | gRPC / Protobuf       | Agent-Core communication          |

## Key Features

* Centralized security event collection
* Event normalization and correlation
* Rule-based threat detection
* Anomaly detection
* Incident management
* Automated response
* Windows and Linux endpoint monitoring
* Database security monitoring
* Configuration snapshots and change detection
* Persistent local event buffering
* Backpressure and telemetry prioritization
* Mutual TLS authentication
* Horizontally scalable Core architecture

## Project Status

🚧 **Active development**

The project is currently under architectural design and prototype development.

## Repositories

Repositories will be added as individual Alyvion components are implemented.

## License

License information will be added with the first public release.
