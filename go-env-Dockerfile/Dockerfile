# 制作基于ubuntu:20.02的镜像,内置go1.17,fish,git,vim
# 构建方法：docker build -t='ubuntu-go:20.04-1.17'
FROM ubuntu:20.04

# 设置标签
LABEL base="ubuntu:20.04" \
      go-version="1.17" \
      git="latest" \
      maintainer="Lo" 

# 安装开发工具
# ADD docker-compose /usr/local/bin/
RUN apt-get update && \
    apt-get install git -y && \
    apt-get install wget -y && \ 
    apt-get install vim -y && \
    apt-get install make -y && \
    apt-get install fish -y 
    # apt-get install net-tools -y && \
    # apt-get install iputils-ping -y 

# 安装go环境
# ADD go1.17.linux-amd64.tar.gz /usr/local/
RUN wget -c  https://studygolang.com/dl/golang/go1.17.linux-amd64.tar.gz -O - |  tar -xz -C /usr/local 
ENV GOROOT=/usr/local/go
ENV PATH=$PATH:$GOROOT/bin
RUN go env -w GOPROXY=https://goproxy.cn,https://gocenter.io,https://goproxy.io,direct && \
    go env -w GO111MODULE=on
