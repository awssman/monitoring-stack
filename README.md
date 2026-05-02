# Server Monitoring Stack

Production-ready server monitoring stack using Docker Compose.

Built as a portfolio project to demonstrate infrastructure automation and monitoring skills.

## Components

| Service        | Port  | Purpose                        |
|---------------|-------|--------------------------------|
| Grafana       | 3000  | Dashboard and visualization    |
| Prometheus    | 9090  | Metrics collection and storage |
| Node Exporter | 9100  | Host system metrics            |
| cAdvisor      | 8080  | Docker container metrics       |

## Quick Start

    git clone https://github.com/awssman/monitoring-stack.git
    cd monitoring-stack
    docker compose up -d

Open Grafana at http://localhost:3000 (admin / admin)

## Features

- One-command deployment
- Auto-provisioned Prometheus datasource in Grafana
- 30-day metric retention
- 7 pre-configured alert rules
- Isolated Docker network
- Persistent data with named volumes
- Container monitoring via cAdvisor

## Alert Rules

| Alert               | Threshold | Duration | Severity |
|---------------------|-----------|----------|----------|
| HighCpuUsage        | > 80%     | 5 min    | warning  |
| CriticalCpuUsage    | > 95%     | 2 min    | critical |
| HighMemoryUsage     | > 85%     | 5 min    | warning  |
| DiskSpaceLow        | > 85%     | 5 min    | warning  |
| DiskSpaceCritical   | > 95%     | 2 min    | critical |
| HostDown            | down      | 1 min    | critical |
| HighNetworkTraffic  | > 100Mbps | 5 min    | warning  |

## File Structure

    monitoring-stack/
    ├── docker-compose.yml
    ├── prometheus/
    │   ├── prometheus.yml
    │   └── alerts.yml
    ├── grafana/
    │   └── provisioning/
    │       ├── datasources/
    │       │   └── prometheus.yml
    │       └── dashboards/
    │           └── dashboards.yml
    └── README.md

## Requirements

- Docker Engine 20.10+
- Docker Compose v2
- Linux host (tested on Debian 12 and Ubuntu 22.04)

## Author

Awssman — IT Systems Administrator
