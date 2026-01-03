---
aliases:
  - Market Making Service
  - algo
tags:
  - service
  - stateful
  - trading
  - algo
  - market-making
dependencies:
  - match-engine
  - postgres
  - Kafka
max-instances: 1
---
## dependencies:
  - Match Engine (GRPC/HTTP)
  - PostgreSQL
  - Apache Kafka


# Flow
1. [[#read_config]]
2. [[#create MatchEngine]]

## read config