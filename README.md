# Jexus x64 Standalone for Linux docker image

Jexus Web Server x64 Standalone in docker.

Usage:

1. Get the image with command:

```sh
docker pull beginor/jexus-x64:5.8.2
```

2. Prepare the directors for volumes:

```sh
mkdir -p "$(pwd)/jexus/conf"
mkdir -p "$(pwd)/jexus/www"
mkdir -p "$(pwd)/jexus/log"
```

3. Run the image with command:

```sh
docker run \
    --detach \
    --name jexus \
    --restart unless-stopped \
    --publish 5820:80 \
    --volume $(pwd)/jexus/www:/var/www \
    --volume $(pwd)/jexus/conf:/usr/jexus/siteconf \
    --volume $(pwd)/jexus/log:/usr/jexus/log \
    beginor/jexus-x64:5.8.2
```
4. Then browse [http://127.0.0.1:5820/info](http://127.0.0.1:5820/info) with
your faverite borwser, see what happens.
