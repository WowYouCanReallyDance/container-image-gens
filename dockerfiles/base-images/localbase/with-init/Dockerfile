## 安装了init，并且容器启动入口为`/sbin/init`。可以使用systemctl，也可以shutdown now关机。
FROM localhost/localbase/debian-base as initable
RUN apt update -y && apt upgrade -y && apt install -y init && apt autoclean -y
ENTRYPOINT ["/sbin/init"]
