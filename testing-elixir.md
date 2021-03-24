**mix test watch without dependency**
```bash
fswatch lib/ test/ | mix test --stale --listen-on-stdin 
```