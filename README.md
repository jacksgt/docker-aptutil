# docker-aptutil

Docker Image for [aptutil](https://github.com/cybozu-go/aptutil) containing `go-apt-cacher` and `go-apt-mirror`.

## Usage

### go-apt-mirror

Mount the configuration file for go-apt-cacher to `/etc/go-apt-cacher.toml` (read-only for added security).

Optionally, mount `/var/spool/go-apt-cacher` for persistence (required for `--read-only`).
```
$ docker container run \
    --read-only \
    -v /etc/go-apt-cacher.toml:/etc/go-apt-cacher.toml:ro' \
    -v /var/spool/go-apt-cacher:/var/spool/go-apt-cacher \
    jacksgt/aptutil /go-apt-cacher
```

### go-apt-mirror

Mount the configuration file for go-apt-cacher to `/etc/apt/mirror.toml` (read-only for added security).

Mount `/var/spool/go-apt-mirror` to store the mirrored files permanently (required for `--read-only`).
```
$ docker container run \
    --read-only \
    -v /etc/go-apt-mirror.toml:/etc/apt/mirror.toml:ro \
    -v /var/spool/go-apt-mirror:/var/spool/go-apt-mirror \
    jacksgt/aptutil /go-apt-mirror
```

## License

Licensed under the MIT License (Expat). See `LICENSE`.
