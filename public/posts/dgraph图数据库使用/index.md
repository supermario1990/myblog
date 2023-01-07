# DGraph图数据库使用


<!--more-->
## 背景

之前做了一个项目，项目中需要追溯生产环节中的生产过程。需求大概是这样, 输入任意的生产序号，查找这个生产序号的后续序号，同时反向查找此前序序号。这其实就是一个有向无环图。因为当时只对关系型数据库和一些nosql数据库比较熟，所以就直接选择了mysql来做存储。在关系型数据库中要表达"图"或者"树"其实是很别扭的，非常不方便。当时做的也比较丑陋，查询性能很差。

其实在这个场景下，使用图数据库是最合适的。目前有两款开源的图数据比较好：`dgraph` 和 `nebula graph`。`nebula graph` 使用c++开发，目前只支持linux。`dgraph` 使用go开发，支持全平台。从网上的资料来看，`nebula graph` 可能在性能上更有优势，但是个人语言喜好问题，我还是选择了 `dgraph`。

## dgraph安装

1.为了更快的体验测试，直接使用docker安装 `dgraph` 服务器:

``` shell
docker run --rm -it -p 8080:8080 -p 9080:9080 dgraph/standalone:v21.12.0
```

2.安装 `dgraph ui` Ratel

```shell
git clone https://github.com/dgraph-io/ratel.git
# Build ratel
# NOTE: ratel needs to be in your GOPATH for this to work.
cd ratel
./scripts/build.prod.sh

# Start the ratel server.
./build/ratel  
# Visit localhost:8000 to use ratel.

#或者使用下面的方式, 我使用的是这种
#Using WebpackDevServer for fast re-compilation of JavaScript
cd client/
npm start
```

直接访问 `http://localhost:3000/`

## dgraph使用

1. mutation

```json

```

---

> 作者: super_mario  
> URL: https://super_mario.gitee.io/posts/dgraph%E5%9B%BE%E6%95%B0%E6%8D%AE%E5%BA%93%E4%BD%BF%E7%94%A8/  

