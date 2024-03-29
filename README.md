# k8s-docker-deployment

**k8s cluster or docker deployment document**

## single-redis

k8s deploy, redis is configured in ConfigMap

```
kubectl apply -f single-redis-conf.yaml
kubectl apply -f single-redis.yaml
```

****

## docker-single-rocketmq

[document](https://www.jianshu.com/p/6ad529a16677)

docker deploy rocketmq

deployment environment: linux/arm64

****

## docker-single-grafana-prometheus

目录下 prometheus.yml 文件为prometheus配置文件

[grafana模版地址](https://grafana.com/grafana/dashboards/)

可下载文档,在grafana中导入json文件，也可记录模版编号 在grafana中填写 系统自动加载

```
// 部署grafana命令
docker-composer -f grafana.yml up -d

```

****

## docker-single-loki

loki-local-config.yaml and promtail-config.yaml is configuration files

```
//deploy loki and promtail
docker-composer -f loki.yml up -d

//need deploy grafana refer to docker-single-grafana-prometheus/grafana.yml
```

****

## docker-multi-es

elasticsearch版本为7.17.9。 v8以上版本默认开启安全验证,不配置会报错
![img.png](picture/img.png)

```
docker-composer -f es.yml up -d
```

#### reference document

- [阳明博客Grafana Loki简明教程](https://www.qikqiak.com/post/grafana-loki-usage/)

****

## docker-multi-clickhouse

```
docker-composer -f clickhouse.yml up -d
```

#### reference document

- [官方文档](https://clickhouse.com/docs)

****

## docker-ubuntu-server

制作ubuntu基础镜像,并配置了ssh, 可本地连接到镜像内操作

```
docker build -t candice0630/ubuntu-server:v1 .
docker-composer -f ubuntu.yml up -d
```

****

## docker-multi-minio

```
docker-composer -f minio.yml up -d
```

reference document

- [官方文档](https://min.io/docs/minio/container/index.html)
- [tips](https://www.jianshu.com/p/da341bffe166)

****

## docker-single-redis

```
docker-composer -f redis.yml up -d
```

****

## k8s-multi-etcd

- [tips](https://blog.csdn.net/kevin_tech/article/details/116906001)

```
//先创建etcd命名空间
1、kubectl create namespace etcd

2、kubectl apply -f etcd-service.yaml

3、cat etcd.yml.tmpl | ./config.bash | kubectl apply -n etcd -f -

4、kubectl apply -f /e3w/configmap.yaml

5、kubectl apply -f /e3w/deployment-service.yaml

```