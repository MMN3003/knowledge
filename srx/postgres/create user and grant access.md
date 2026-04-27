```
CREATE ROLE developer WITH LOGIN PASSWORD 'TRy@34%38!@fxjsdW@3*';

GRANT CONNECT ON DATABASE exchange_history TO developer;

GRANT USAGE ON SCHEMA public TO developer;

GRANT SELECT ON TABLE public.balance_history TO developer;

REVOKE ALL ON ALL TABLES IN SCHEMA public FROM developer;

REVOKE CREATE ON SCHEMA public FROM developer;
```

TRy@34%38!@fxjsdW@3*