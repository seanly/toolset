FROM ubuntu:22.04

ARG DEBIAN_FRONTEND=noninteractive

SHELL ["/bin/bash", "-c"]

ENV TZ=Asia/Shanghai
RUN set -eux;\
    apt update && \
    apt install -y --no-install-recommends \
        apt-transport-https ca-certificates\
        build-essential\
        procps \
        curl wget \
        xz-utils\
        file \
        git && \
    ln -snf /usr/share/zoneinfo/$TZ /etc/localtime &&\
    echo $TZ > /etc/timezone && \
    apt install -y --no-install-recommends tzdata && \
    dpkg-reconfigure --frontend noninteractive tzdata

COPY init.sh /

RUN git clone --depth 1 https://github.com/Homebrew/brew ~/.linuxbrew/Homebrew \
    && mkdir ~/.linuxbrew/bin \
    && ln -s ../Homebrew/bin/brew ~/.linuxbrew/bin \
    && eval $(~/.linuxbrew/bin/brew shellenv) \
    && brew --version \
    && bash /init.sh