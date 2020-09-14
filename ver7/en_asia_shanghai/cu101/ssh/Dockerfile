FROM ccr.ccs.tencentyun.com/lilinxiong/en_centos:cu101_base

RUN yum update -y \
    && yum install -y openssh-server gcc gcc-c++ rsync

RUN /bin/echo "root" | passwd --stdin root

RUN ssh-keygen -t rsa -f /etc/ssh/ssh_host_rsa_key \
    && ssh-keygen -t rsa -f /etc/ssh/ssh_host_ecdsa_key \
    && ssh-keygen -t rsa -f /etc/ssh/ssh_host_ed25519_key

RUN /bin/sed -i 's/.*session.*required.*pam_loginuid.so.*/session optional pam_loginuid.so/g' /etc/pam.d/sshd \
    && /bin/sed -i 's/UsePAM yes/UsePAM no/g' /etc/ssh/sshd_config \
    && /bin/sed -i "s/#UsePrivilegeSeparation.*/UsePrivilegeSeparation no/g" /etc/ssh/sshd_config

RUN yum clean all \ 
    && rm -rf /var/cache/yum/*

EXPOSE 22

WORKDIR /root/

CMD ["/usr/sbin/sshd","-D"]