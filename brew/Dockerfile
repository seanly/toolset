FROM ubuntu:22.04

RUN apt update && \
    apt-get install build-essential procps curl file git -y

RUN git clone https://github.com/Homebrew/brew ~/.linuxbrew/Homebrew \
    && mkdir ~/.linuxbrew/bin \
    && ln -s ../Homebrew/bin/brew ~/.linuxbrew/bin \
    && eval $(~/.linuxbrew/bin/brew shellenv) \
    && brew --version

COPY init.sh /
RUN bash /init.sh