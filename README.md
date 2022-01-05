# k8s-docker-deployment

> k8s cluster or docker deployment document

## single-redis

k8s deploy, redis is configured in ConfigMap

```
kubectl apply -f single-redis-conf.yaml
kubectl apply -f single-redis.yaml
```

## rocketmq

[document](https://www.jianshu.com/p/6ad529a16677)

docker deploy rocketmq

deployment environment: linux/arm64