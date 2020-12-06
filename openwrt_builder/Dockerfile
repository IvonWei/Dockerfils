FROM debian
MAINTAINER madwind.cn@gmail.com

RUN set -ex && \
    apt update && \
    apt install -y subversion g++ zlib1g-dev build-essential git python python3 python3-distutils libncurses5-dev gawk gettext unzip file libssl-dev wget libelf-dev ecj fastjar java-propose-classpath rsync upx

ENV GOPROXY=https://mirrors.aliyun.com/goproxy/