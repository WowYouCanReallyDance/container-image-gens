FROM debian-base as openjdk21-base
ARG OPEN_JDK_PACK_NAME=openjdk-21.0.2_linux-x64_bin.tar.gz
RUN mkdir -p /usr/lib/jvm \
    && cd /usr/lib/jvm \
    && curl -O https://d6.injdk.cn/openjdk/openjdk/21/$OPEN_JDK_PACK_NAME \
    && tar -zxvf $OPEN_JDK_PACK_NAME \
    && rm -rf $OPEN_JDK_PACK_NAME
ENV JAVA_HOME=/usr/lib/jvm/jdk-21.0.2/
ENV PATH=$PATH:$JAVA_HOME/bin
