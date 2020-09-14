FROM nvidia/cuda:10.1-base-centos7

RUN /bin/cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
    && echo 'Asia/Shanghai' >/etc/timezone

RUN yum clean all \
    && rm -rf /var/cache/yum/*

ENV LC_ALL "zh_CN.utf8"

WORKDIR ~