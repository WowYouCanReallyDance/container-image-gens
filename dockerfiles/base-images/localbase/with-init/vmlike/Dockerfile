FROM debian:bullseye as debian-base
RUN echo "deb http://mirrors.tuna.tsinghua.edu.cn/debian/ bullseye main contrib non-free \
          deb http://mirrors.tuna.tsinghua.edu.cn/debian/ bullseye-updates main contrib non-free \
          deb http://mirrors.tuna.tsinghua.edu.cn/debian/ bullseye-backports main contrib non-free \
          deb http://mirrors.tuna.tsinghua.edu.cn/debian-security bullseye-security main contrib non-free" > /etc/apt/sources.list \
    && apt update \
    && apt upgrade -y \
    && apt install -y curl htop procps git \
    && apt autoclean -y


FROM debian-base as vmlike-base
ARG SSHD_CONFIG=/etc/ssh/sshd_config
WORKDIR /root/dev
RUN apt update \
    && apt upgrade -y \
    && apt install -y init zsh vim ssh iproute2 \
    && apt autoclean -y \
    && sed -i '/#PermitRootLogin prohibit-password/a PermitRootLogin yes' $SSHD_CONFIG \
    && chsh -s $(which zsh)
ENTRYPOINT ["/sbin/init"]
