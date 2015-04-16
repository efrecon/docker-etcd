# docker-etcd

This repository contains two minimal components to run `etcd`-dependent
applications.  Both are placed on top of [Alpine] Linux to keep their size down.

* The `etcd` component has volume export, meaning that it is able to keep the
  client cache on a locally mounted volume if necessary.  All "old" and IANA
  ports are exported and no other options apart from the exported data directory
  are specified for maximum flexibility.

* The `etcdctl` component automatically uses the local host as an endpoint,
  albeit on the old API port, i.e. 4001 (rather than the new IANA port 2380).

My goal is to follow the latest releases of `etcd` as closely as possible.
Currently, this is at version v2.0.9, meaning the latest.

  [Alpine]: http://gliderlabs.viewdocs.io/docker-alpine
