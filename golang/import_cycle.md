**Import cycle
今天碰到一个非常规的import cycle问题，记录一下：
```
1. multi-cloud原本编译正常；
2. 为了安装go_s3tests(https://github.com/ceph/go_s3tests)，按照提示执行了cd;go get -v -d ./...
3. 再次到multi-cloud目录下执行make docker，提示import cycle not allowed。
```
解决办法：
```
1. 清理go安装包：rm -rf /usr/local/go; rm -rf /usr/bin/go；
2. 重新安装go：tar -xzf go1.12.1.linux-amd64.tar.g -C /usr/local; ln -s /usr/local/go/bin/*.
```
疑问：
  go get -v -d ./...到底做了什么，为什么会导致import cycle?
