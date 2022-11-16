# KIND 创建K8S集群

```shell
kind create cluster \
    --config /home/project/k8s/config.yaml \
    --image registry.cn-hangzhou.aliyuncs.com/smartide/nestybox-kindestnode:v1.20.7
```

# 执行docker build并推送镜像仓库
```shell
docker build -t registry.cn-hangzhou.aliyuncs.com/chileeb/smartide-calc:v1 .
docker login --username=chileeb registry.cn-hangzhou.aliyuncs.com
docker push registry.cn-hangzhou.aliyuncs.com/chileeb/smartide-calc:v1
```

# 直接导入镜像，加速启动
```shell
kind load docker-image registry.cn-hangzhou.aliyuncs.com/chileeb/smartide-calc:v1
```

# 部署应用程序
```shell
kubectl apply -f k8s/deploy/boathouse-calculator-deployment.yaml
```
