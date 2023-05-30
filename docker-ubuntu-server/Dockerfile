FROM ubuntu:20.04
ENV TZ Asia/Shanghai
ENV LANG zh_CN.UTF-8
RUN echo 'root:root' |chpasswd
# 更换镜像源
RUN echo "deb http://mirrors.ustc.edu.cn/ubuntu-ports/ focal main restricted universe multiverse\n \
deb http://mirrors.ustc.edu.cn/ubuntu-ports/ focal-security main restricted universe multiverse \n \
deb http://mirrors.ustc.edu.cn/ubuntu-ports/ focal-updates main restricted universe multiverse\n	\
deb http://mirrors.ustc.edu.cn/ubuntu-ports/ focal-backports main restricted universe multiverse\n"\
            > /etc/apt/sources.list        \
            && apt update && apt install -y \
			openssh-server \
			vim \
			&& apt clean \
			&& rm -rf /tmp/* /var/lib/apt/lists/* /var/tmp* \
			&& echo "PermitRootLogin yes" >> /etc/ssh/sshd_config
RUN mkdir /var/run/sshd

EXPOSE 22
CMD ["/usr/sbin/sshd","-D"]