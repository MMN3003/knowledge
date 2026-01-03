dependecies:
	- match engin
	- postgress
	- kafka





start service:
	1. read exchange pair from `config.toml`
	2. create `MatchEngine` instance for market making broker, requirements:
		1. match engine grpc instance
		2. match engine http instance
	3. seed `MatchEngine`
		1. fetch best ask and bid from match engine grpc `OrderBookDepth` 
		2. calculate spreed by this formula
			1. spread = ( (best ask - best bid) / best bid ) * 100
	4. `NewMatchEngineHandler`?
	5. `prepareExchanges`?
	6. create instance of `KafkaPresentation`, requirements:
		1. `MatchEngineHandler`
		2. `SpreadBot`s
	7. consume kafka topics
		1. `trades`: order executed or matched in system
			1. who send it?
			2. 
		2. `depth`: