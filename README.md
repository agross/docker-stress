# docker-stress

docker stress testing using [stress](http://linux.die.net/man/1/stress).

## Usage

```sh
docker run -it --rm [docker run args] agross/stress [stress args]

# e.g. allow container to allocate no more than 100MB * 2 (memory + swap), but try to allocate 201MB.
SIZE=100 docker run -it --rm --memory ${SIZE}m agross/stress --vm 1 --vm-bytes $((($SIZE * 2 + 1)))M --vm-hang 0
```

[More information.](https://goldmann.pl/blog/2014/09/11/resource-management-in-docker)
