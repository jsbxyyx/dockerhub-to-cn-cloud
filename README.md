# dockerhub-to-cn-cloud
dockerhub 拉取公共镜像到国内云

## 阿里云 容器镜像服务ACR个人版

开通教程

https://help.aliyun.com/zh/acr/user-guide/create-a-container-registry-personal-edition-instance


> 把命名空间设置为公开，否则在拉取镜像时需要登录账号


配置私有信息

在 settings -> secrets and variables -> Actions -> Repository secrets

```
DOCKER_URL: 公网地址
DOCKER_USER: 用户名
DOCKER_PASSWORD: 密码
DOCKER_NAMESPACE: 命名空间
```

在Actions中找到dockerhub-to-cn-cloud，点击Run workflow，输入镜像名称

示例1：nacos/nacos-server:v2.4.3

```
docker pull ${DOCKER_URL}/${DOCKER_NAMESPACE}/nacos_nacos-server:v2.4.3
```

示例2：redis:5.0

```
docker pull ${DOCKER_URL}/${DOCKER_NAMESPACE}/redis:5.0
```
