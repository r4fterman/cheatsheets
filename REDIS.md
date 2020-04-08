# REDIS

## Delete all keys in Redis
```
    redis-cli KEYS "key:*" | xargs redis-cli DEL
```