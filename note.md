## for devops
docker build -t ygsoft-xxx:v6.7.0-20201130 .

docker save ygsoft-xxx:v6.7.0-20201130 > ygsoft-xxx-v6.7.0-20201130

docker tag ygsoft-xxx:v6.7.0-20201130 127.0.0.1:5000/ywzt/ygsoft-xxx:v6.7.0-20201130

docker push 127.0.0.1:5000/ywzt/ygsoft-xxx:v6.7.0-20201130

## 过多无意义的层，会造成镜像膨胀过大
FROM jre-alpha
RUN /bin/cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && echo 'Asia/Shanghai' >/etc/timezone 
ADD ygsoft /ygsoft

## 从宿主机拷贝文件到容器
docker cp 宿主机目录或文件 容器名称:路径

## 每一迭代都需要建立新的迭代分支，以及对应的热修复分支

## ES不能以root身份启动，
   useradd testuser && chown testuser /ES/elasticsearch
   su - testuser
   exit 退出并切回普通用户

## 启动脚本
java -Dserver.port=$PORT -Dspring.config.location=$PATH -Dfile.encoding=utf-8 -Dapp.name=$NAME -jar $JAR_NAME > /dev/null 2>&1 &
## 停止脚本
kill -9 $(ps -ef | grep 进程特征 | grep -v grep | awk '{print $2}')
## 变量赋值
sp_pid=`ps -ef | grep 进程特征 | grep -v grep | awk '{print $2}'`

