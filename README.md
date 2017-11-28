# docker-aptutil

Docker Image for [aptutil](https://github.com/cybozu-go/aptutil) containing `go-apt-cacher` and `go-apt-mirror`.

## Usage

### go-apt-mirror

Mount the configuration file for go-apt-cacher to `/etc/go-apt-cacher.toml` (read-only for added security).
```
$ docker container run -v '/etc/go-apt-cacher.toml:/etc/go-apt-cacher.toml:ro' jacksgt/aptutil go-apt-cacher
```

### go-apt-mirror

Mount the configuration file for go-apt-cacher to `/etc/apt/mirror.toml` (read-only for added security).
```
$ docker container run -v '/etc/go-apt-mirror.toml:/etc/apt/mirror.toml:ro' jacksgt/aptutil go-apt-mirror
```

## License

Licensed under the MIT License (Expat). See `LICENSE`.
