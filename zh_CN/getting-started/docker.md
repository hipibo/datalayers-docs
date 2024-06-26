# 通过 Docker 快速体验 Datalayers

本文将介绍如何通过 Docker 快速体验 Datalayers 的各项功能。若未安装 Docker，请至<a href="https://docs.docker.com/get-docker/" target="_blank">Docker官方文档</a>查看并安装。


## 通过 Docker 启动 Datalayers

首先，请执行以下命令拉取最新的 Datalayers 镜像：

``` bash
docker pull datalayers/datalayers:nightly
```

或者拉取指定版本的镜像：

``` bash
docker pull datalayers/datalayers:1.0.0
```

执行以下命令，启动一个 Datalayers 容器：

``` bash
docker run --name my-datalayers -d \
  -v ./my-data:/var/lib/datalayers/storage \
  datalayers/datalayers:nightly \
  datalayers standalone
```

::: tip
其中`./my-data`是期望容器运行结束后数据能持久化的目录。
:::

通过 `docker ps` 命令确认容器已经正常启动后，执行以下命令进入容器：

``` bash
docker exec -it <your_container_name> bash
```

进入容器后，可通过[命令行工具](./command-line-tool.md)快速体验 Datalayers 的各项功能。