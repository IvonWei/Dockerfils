FROM alpine

LABEL maintainer="madwind.cn@gmail.com" \
        org.label-schema.name="acme"

RUN apk add --no-cache curl bash openssl tzdata && \
    curl https://get.acme.sh | sh && \
	cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
  	echo "Asia/Shanghai" >  /etc/timezone && \
    rm -rf /var/cache/apk/*

WORKDIR /root/.acme.sh/