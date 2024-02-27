FROM initable as vmlike-base
ARG GITHUB_URL=https://github.com
ARG GITHUB_PROXY=https://mirror.ghproxy.com
ARG OH_MY_ZSH_INSTALL_SHELL_URL=https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/
ARG OH_MY_ZSH_INSTALL_SHELL_FILE_NAME=install.sh
RUN apt update -y && apt upgrade -y && apt autoclean -y \
    && apt install -y vim zsh ssh iproute2 \
    && mkdir -p /root/dev && cd /root/dev \
    && curl -O $GITHUB_PROXY/$OH_MY_ZSH_INSTALL_SHELL_URL$OH_MY_ZSH_INSTALL_SHELL_FILE_NAME \
    && sed -i 's|${GITHUB_URL}|${GITHUB_PROXY}/${GITHUB_URL}|g' $OH_MY_ZSH_INSTALL_SHELL_FILE_NAME \
    && chmod +x $OH_MY_ZSH_INSTALL_SHELL_FILE_NAME
