#源镜像
FROM golang:latest
#-alpine
#FROM golang:1.17 as build

ENV GOPROXY https://goproxy.cn,direct

## 在docker的根目录下创建相应的使用目录
RUN mkdir -p /www/webapp
## 设置工作目录
WORKDIR /www/webapp

RUN apt-get update && \
    apt-get install -y wget && \
    apt-get -y install unoconv &&\
    apt-get -y install fontconfig xfonts-utils




EXPOSE 8080
#暴露端口
EXPOSE 9876

#fc-list :lang=zh
#https://installati.one/kalilinux/
