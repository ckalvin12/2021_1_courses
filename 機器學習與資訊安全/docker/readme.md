
# docker ==> Dockerfile

# docker-compose ==> docker-compose.yml

# k8s ==> 

# docker ==> Dockerfile
```
https://ithelp.ithome.com.tw/articles/10191016
```
## Dockerfile
```
FROM centos:7
MAINTAINER jack

RUN yum install -y wget

RUN cd /

ADD jdk-8u152-linux-x64.tar.gz /

RUN wget http://apache.stu.edu.tw/tomcat/tomcat-7/v7.0.82/bin/apache-tomcat-7.0.82.tar.gz
RUN tar zxvf apache-tomcat-7.0.82.tar.gz

ENV JAVA_HOME=/jdk1.8.0_152
ENV PATH=$PATH:/jdk1.8.0_152/bin
CMD ["/apache-tomcat-7.0.82/bin/catalina.sh", "run"]
```
```
FROM： 使用到的 Docker Image 名稱，今天使用 CentOS

MAINTAINER： 用來說明，撰寫和維護這個 Dockerfile 的人是誰，也可以給 E-mail的資訊

RUN： RUN 指令後面放 Linux 指令，用來執行安裝和設定這個 Image 需要的東西

ADD： 把 Local 的檔案複製到 Image 裡，如果是 tar.gz 檔複製進去 Image 時會順便自動解壓縮。Dockerfile 另外還有一個複製檔案的指令 COPY 未來還會再介紹

ENV： 用來設定環境變數

CMD： 在指行 docker run 的指令時會直接呼叫開啟 Tomcat Service
```
```
docker build -t mytomcat . --no-cache

使用 --no-cache 的主要原因，是避免在 Build Docker image 時被 cache 住，
而造成沒有 build 到修改過的 Dockerfile。
```
```
docker run mytomcat
```



KALI ROOT ==> /root/DOCKER
                       /demo1: ==> redis
                         dockerfile
                         
                       /demo2  ==> python 爬蟲                    

# spark

docker pull bitnami/spark

##
```
https://hub.docker.com/r/prom/prometheus/
```
#
```
version: '2'

services:
  spark:
    image: docker.io/bitnami/spark:3-debian-10
    environment:
      - SPARK_MODE=master
      - SPARK_RPC_AUTHENTICATION_ENABLED=no
      - SPARK_RPC_ENCRYPTION_ENABLED=no
      - SPARK_LOCAL_STORAGE_ENCRYPTION_ENABLED=no
      - SPARK_SSL_ENABLED=no
    ports:
      - '8080:8080'
  spark-worker-1:
    image: docker.io/bitnami/spark:3-debian-10
    environment:
      - SPARK_MODE=worker
      - SPARK_MASTER_URL=spark://spark:7077
      - SPARK_WORKER_MEMORY=1G
      - SPARK_WORKER_CORES=1
      - SPARK_RPC_AUTHENTICATION_ENABLED=no
      - SPARK_RPC_ENCRYPTION_ENABLED=no
      - SPARK_LOCAL_STORAGE_ENCRYPTION_ENABLED=no
      - SPARK_SSL_ENABLED=no
  spark-worker-2:
    image: docker.io/bitnami/spark:3-debian-10
    environment:
      - SPARK_MODE=worker
      - SPARK_MASTER_URL=spark://spark:7077
      - SPARK_WORKER_MEMORY=1G
      - SPARK_WORKER_CORES=1
      - SPARK_RPC_AUTHENTICATION_ENABLED=no
      - SPARK_RPC_ENCRYPTION_ENABLED=no
      - SPARK_LOCAL_STORAGE_ENCRYPTION_ENABLED=no
      - SPARK_SSL_ENABLED=no

https://raw.githubusercontent.com/bitnami/bitnami-docker-spark/master/docker-compose.yml
```
