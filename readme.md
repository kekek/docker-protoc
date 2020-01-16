
### 说明 
 
go-micro 老版本的proto生成工具


### 运行

运行下面的命令会执行当前路径下的 entrypoint.sh 脚本文件


```
docker run --rm -it -v $(pwd):/project kekek/protoc:v4
```

### 生成文件

- protobuf 

https://github.com/golang/protobuf/archive/v1.0.0.zip


- micro-proto-gen

https://github.com/kekek/old-micro-protobuf/archive/master.zip

- namely/protoc:1.26_0

- golang:1.13.6-alpine3.11
