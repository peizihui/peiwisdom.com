 1.  下载最新分支；

git clone  -b released/v1.0.6.0 [https://github.com/hpb-project/go-hpb.git](https://github.com/hpb-project/go-hpb.git)


2.  进到当前目录下；
cd  go-hpb


![](http://q8xc9za4f.bkt.clouddn.com/corejava/1.cdgohpb.png)

3.  go-hpb路径下执行   docker build -t hpbbc/go-hpbv1060 .  注意 “.” ，当前路径；
![](http://q8xc9za4f.bkt.clouddn.com/corejava/2.docker-build.png)

4.  导出镜像；docker save --output  go-hpbv1060.tar.gz   hpbbc/go-hpbv1060

![](http://q8xc9za4f.bkt.clouddn.com/corejava/3.docker-save.png)


5.1   导出的镜像可以复制到其他服务器上使用， docker load < go-hpbv1060.tar.gz 

![](http://q8xc9za4f.bkt.clouddn.com/corejava/4.docker-load.png)

5.2 或者上传镜像到docker 仓库； docker push hpbbc/go-hpb
![](http://q8xc9za4f.bkt.clouddn.com/corejava/5.docker-push.png)

6.1 重新拉取docker 镜像；  docker pull  hpbbc/go-hpb


6.2 重新启动；

docker run -itd --privileged=true --restart=always -v /home/ghpb-bin/node/:/root/node/ -p 8545:8545 -p 30303:30303 -p 8546:8546 --name ghpb1060 hpbbc/go-hpbbc:latest --datadir /root/node/data --networkid 100 --verbosity 1 --rpc --rpcaddr 0.0.0.0 --rpcapi  hpb,web3,admin,txpool,debug,personal,net,miner,prometheus --syncmode full --nodetype synnode console



7. 检查版本号   

    docker run --privileged=true hpbbc/go-hpb:latest version

![](http://q8xc9za4f.bkt.clouddn.com/corejava/6.docker-version.png)