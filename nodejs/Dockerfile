FROM seanly/toolset:brew

COPY ./rootfs /

ARG NODE_VER=v18.19.0
ENV NODE_VER=${NODE_VER}

ARG YARN_VER=v1.22.21
ENV YARN_VER=${YARN_VER}

RUN set -eux \
    ; OS="$(uname | tr '[:upper:]' '[:lower:]')" \
    ; ARCH="$(uname -m | sed -e 's/x86_64/x64/' -e 's/\(arm\)\(64\)\?.*/\1\2/' -e 's/aarch64$/arm64/')" \
    ; mkdir -p /opt/node/ \
    ; mkdir -p /opt/yarn/ \
    && wget -c https://nodejs.org/dist/${NODE_VER}/node-${NODE_VER}-linux-${ARCH}.tar.xz -O - | tar -Jx --strip-components=1 -C /opt/node \
    && wget -c https://github.com/yarnpkg/yarn/releases/download/${YARN_VER}/yarn-${YARN_VER}.tar.gz -O - | tar -zx --strip-components=1 -C /opt/yarn \
    && chmod 755 /opt/node/bin/node \
    && chmod 755 /opt/node/bin/npm \
    && chmod 755 /opt/yarn/bin/yarn \
    && mkdir -p /opt/node/etc/ \
    && mkdir -p /opt/global-modules \
    && mkdir -p /opt/yarn-global\
    && mkdir -p /opt/yarn-cache

ENV PATH=/opt/node/bin:/opt/yarn/bin:$PATH
ENV PATH=./node_modules/.bin:/root/.config/yarn/global/node_modules/.bin:/opt/global-modules/bin:/opt/yarn-global/node_modules/.bin:$PATH

ARG PNPM_VERSION=6.35.1
ENV PNPM_VERSION=${PNPM_VERSION}

RUN set -eux;\
  curl -sL https://unpkg.com/@pnpm/self-installer | /opt/node/bin/node

ENV PNPM_HOME="/root/.local/share/pnpm"
ENV PATH="$PNPM_HOME:$PATH"
