FROM ccr.ccs.tencentyun.com/lilinxiong/zh_centos:cu101_base

LABEL maintainer "lilinxiong <lilinxiong1997@gmail.com>"

COPY nginx.repo /etc/yum.repos.d/

RUN yum clean all \
    && yum makecache \
    && yum update -y \
    && yum install -y expect python3 wget openssh-clients ftp yum-utils nginx gcc gcc-c++ \
    && yum clean all \
    && rm -rf /var/cache/yum/*

RUN mkdir /root/service/

WORKDIR /root/

RUN ln -sf /etc/nginx/conf.d ./conf.d

RUN rm -vf /root/conf.d/default.conf

COPY VouCardService.conf /root/conf.d/

CMD ["python3", "setup.py"]