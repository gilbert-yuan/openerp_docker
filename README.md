# gooderp_docker
–name 指定容器名称 gooderp是容器名称

-i 交互模式运行，可以ssh连上 ssh 连上的指令是 docker exec -i -t gooderp /bin/bash

-d 后台运行

-p 映射一个容器的端口到主机的端口 9999主机端口 8888 容器端口

-v 映射一个主机目录到容器的目录 /home/addons是主机目录 /~/extra-addons是容器的第三方模块目录
成功以后，那可以用 http://xxx:9999 来访问了 其实xx为服务器的域名或ip
docker logs -f gooderp

查看正在运行的容器
docker ps

查看正在运行的容器的端口
docker port gooderp
-e 设置环境变量 当要添加python依赖包时可以调用本地的 python 环境
 docker run -name=gooderp -i -d -t -p 9999:8888  -v /home/addons:/~/extra-addons -e PYTHONPATH='/python_path' gilbertyuan/gooderp
 
docker run -name=gooderp -i -d -t -p 9999:8888  -v /home/yuan/myerp/gooderp_addons:/~/gooderp_addons  gilbertyuan/gooderp