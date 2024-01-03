ARG VERSION=8u372-b07-jdk-jammy
FROM eclipse-temurin:${VERSION}

ENV TZ=Asia/Shanghai
ENV LANG=en_US.UTF-8 LANGUAGE=en_US:en LC_ALL=en_US.UTF-8
RUN apt-get update && \
    apt-get install -y --no-install-recommends neovim net-tools iputils-ping telnet zip unzip wget tzdata curl ca-certificates fontconfig locales && \
    echo "en_US.UTF-8 UTF-8" >> /etc/locale.gen