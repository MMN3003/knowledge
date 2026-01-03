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

# Flows
- [[#Initialization Flow]]
- 
## Initialization Flow
1.  [[#Load Configuration]] read exchange pair from `config.toml`
2.  [[#Create MatchEngine Instance]] create `MatchEngine` instance for market making broker.
3. seed `MatchEngine`		
4. [[#NewMatchEngineHandler]]?
5. [[#prepareExchanges]]?
6. [[#Create KafkaPresentation]] create instance of `KafkaPresentation`
7. [[#Consume Kafka]] topics
8. [[#Start HTTP server]]
		


### Load Configuration
### Create MatchEngine Instance
requirements:
		1. match engine grpc instance
		2. match engine http instance
### Seed MatchEngine
1. fetch best ask and bid from match engine grpc `OrderBookDepth` 
2. [[#Calculate Spread]] and set it
#### Calculate Spread
calculate spreed by this formula
```
spread = ( (best ask - best bid) / best bid ) * 100 
```

### NewMatchEngineHandler

### prepareExchanges

### Create KafkaPresentation
requirements:
1. `MatchEngineHandler`
2. `SpreadBot`s

### Consume Kafka
#### Kafka Topics

| Topic name | Sender | Event                               | Link        |
| ---------- | ------ | ----------------------------------- | ----------- |
| `trades`   | ?      | order executed or matched in system | [[#Trades]] |
| `depth`    | ?      | order place                         | [[#Depth]]  |

##### Trades
1. `NewOrderExecuteEvent`
	1. if one side of trade was a bot an `ExecutedOrder` sends to `ExecutedOrder` channel
	2.  who listen to this channel?
2. `UpdateLastTrades` update last price of trade market according to trade price
3. delete or update(amount) of bot order matched in this trade
4. commit message to kafka

##### Depth
1. commit message to kafka at the first step
2. `UpdateSpreadData`
	1. calculate and update spreed again [[#Calculate Spread]]
### Start HTTP server
