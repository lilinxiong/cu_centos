FROM ccr.ccs.tencentyun.com/lilinxiong/zh_centos:cu101_base

LABEL maintainer "lilinxiong <lilinxiong1997@gmail.com>"

RUN yum install -y python3 \
    && rm -rf /var/cache/yum/*

RUN mkdir /root/service/

WORKDIR /root/

CMD ["python3", "setup.py"]