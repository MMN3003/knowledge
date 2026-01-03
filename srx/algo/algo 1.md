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


# Initialization Flow
1.  [[#Load Configuration]] read exchange pair from `config.toml`
2.  [[#Create MatchEngine Instance]] create `MatchEngine` instance for market making broker.
3. seed `MatchEngine`
		
	4. `NewMatchEngineHandler`?
	5. `prepareExchanges`?
	6. create instance of `KafkaPresentation`, requirements:
		1. `MatchEngineHandler`
		2. `SpreadBot`s
	7. consume kafka topics
		1. `trades`: order executed or matched in system
			1. who send it?
			2. `NewOrderExecuteEvent`
				1. if one side of trade was a bot an `ExecutedOrder` sends to `ExecutedOrder` channel
				2.  who listen to this channel?
			3. `UpdateLastTrades` update last price of trade market according to trade price
			4. delete or update(amount) of bot order matched in this trade
			5. commit message to kafka
		2. `depth`:
			1. who sent it?
			2. commit message to kafka at the first step
			3. `UpdateSpreadData`
				1. calculate and update spreed again [[#spread]]


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
