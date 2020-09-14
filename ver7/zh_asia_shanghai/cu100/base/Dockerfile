FROM nvidia/cuda:10.0-base-centos7

RUN yum -y install kde-l10n-Chinese \
    && yum -y reinstall glibc-common \
    && localedef -c -f UTF-8 -i zh_CN zh_CN.utf8 \
    && echo "export LC_ALL=zh_CN.utf8" >> /etc/profile

RUN /bin/cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
    && echo 'Asia/Shanghai' >/etc/timezone

RUN yum clean all \
    && rm -rf /var/cache/yum/*

ENV LC_ALL "zh_CN.utf8"

WORKDIR ~