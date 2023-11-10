FROM alpine

#RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.tuna.tsinghua.edu.cn/g' /etc/apk/repositories
RUN apk update && apk add --update --no-cache curl 

COPY --from=quay.io/coreos/etcd:v3.5.10 /usr/local/bin/etcdctl /usr/bin/etcd
COPY --from=quay.io/coreos/etcd:v3.5.10 /usr/local/bin/etcdctl /usr/bin/etcdctl
COPY --from=quay.io/coreos/etcd:v3.5.10 /usr/local/bin/etcdctl /usr/bin/etcdutl
