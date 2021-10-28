# project1-infra

```shell
helm install zookeeper bitnami/zookeeper \
  --set replicaCount=3 \
  --set auth.enabled=false \
  --set allowAnonymousLogin=true

helm install kafka bitnami/kafka \
--set zookeeper.enabled=false \
--set replicaCount=3 \
--set deleteTopicEnable=true \
--set externalZookeeper.servers=zookeeper.default.svc.cluster.local

helm install my-release bitnami/redis-cluster
```
