# Quickly Start

## Develop in local

通过IDE运行[StartupApplication](/-provider/src/main/java//StartupApplication.java)

### Swagger

- **swagger ui**：[/swagger-ui.html](http://127.0.0.1:8080/swagger-ui.html)
- **swagger json**：[/v2/api-docs](http://127.0.0.1:8080/v2/api-docs)

## Build

### *.jar

```bash
$ mvn clean package -DskipTests
```

### Image

```bash
$ PROJECT_HOME=$PWD \
APP_NAME= \
VERSION=1.0.0 \
sh build.sh
```

或者

```bash
$ PROJECT_HOME=$PWD \
IMAGE_NAME=:v1.0.0 \
sh build.sh
```

## Deploy

### Start via process

```bash
$ mvn clean package
$ java -jar ./-provider/target/app.jar
```

### Start via container

```bash
$ sh start-code.sh [-bl] [-p port] [-v version]
```

- -b: 是否从本地构建镜像
- -l: 是否在启动后输出容器日志
- -p: 指定容器映射端口号（默认8080）
- -v: 指定构建镜像的版本号（默认1.0.0）

如果需要自定义启动命令，可以自行修改[`run.sh`](/run.sh)。
