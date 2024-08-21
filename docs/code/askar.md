## Difference between anoncreds and askar

https://github.com/rngadam/aries-cloudagent-python/blob/3447dc89fbe9b498139705a2b1ac7c69616b0154/aries_cloudagent/config/default_context.py#L144-L156

## Minimal askar

```
scripts/run_docker start --log-level debug  --wallet-type askar --wallet-name $(whoami) --wallet-key mysecretkey --endpoint http://localhost:8080 --no-ledger --inbound-transport http 0.0.0.0 8001 --outbound-transport http
```

wallet is saved here:

/root/.aries_cloudagent/wallet/user/sqlite.db

