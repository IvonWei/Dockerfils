FROM alpine

ARG FRP_VERSION=0.33.0

LABEL maintainer="madwind.cn@gmail.com" \
        org.label-schema.name="frpc" \
        org.label-schema.version=$FRP_VERSION

RUN set -ex && \
    sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g' /etc/apk/repositories && \
    apk add --no-cache tzdata && \
    wget https://github.com/fatedier/frp/releases/download/v${FRP_VERSION}/frp_${FRP_VERSION}_linux_amd64.tar.gz && \
    tar -zxf frp_${FRP_VERSION}_linux_amd64.tar.gz && \
    cd frp_${FRP_VERSION}_linux_amd64 && \
    mkdir /frpc && \
    mkdir /config && \
    mv frpc frpc_full.ini /frpc && \
    cd .. && \
    rm -rf *.tar.gz frp_${FRP_VERSION}_linux_amd64 && \
   	echo "Asia/Shanghai" >  /etc/timezone && \
    rm -rf /var/cache/apk/*

COPY rootfs /

ENTRYPOINT ["/usr/bin/entrypoint.sh"]