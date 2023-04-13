## 👋 Welcome to coolify 🚀  

coolify README  
  
  
## Requires scripts to be installed  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 systemmgr --config && systemmgr install scripts  
```

## Automatic install/update  

```shell
dockermgr update coolify
```

OR

```shell
mkdir -p "$HOME/.local/share/srv/docker/coolify/rootfs"
git clone "https://github.com/dockermgr/coolify" "$HOME/.local/share/CasjaysDev/dockermgr/coolify"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/coolify/rootfs/." "$HOME/.local/share/srv/docker/coolify/rootfs/"
```

## via command line  

```shell
docker pull casjaysdevdocker/coolify:latest && \
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-coolify \
--hostname casjaysdev-coolify \
-e TZ=${TIMEZONE:-America/New_York} \
-v $HOME/.local/share/srv/docker/coolify/rootfs/data:/data:z \
-v $HOME/.local/share/srv/docker/coolify/rootfs/config:/config:z \
-p 80:80 \
casjaysdevdocker/coolify:latest
```

## via docker-compose  

```yaml
version: "2"
services:
  coolify:
    image: casjaysdevdocker/coolify
    container_name: coolify
    environment:
      - TZ=America/New_York
      - HOSTNAME=casjaysdev-coolify
    volumes:
      - $HOME/.local/share/srv/docker/coolify/rootfs/data:/data:z
      - $HOME/.local/share/srv/docker/coolify/rootfs/config:/config:z
    ports:
      - 80:80
    restart: always
```

## Author  

📽 dockermgr: [Github](https://github.com/dockermgr) 📽  
🤖 casjay: [Github](https://github.com/casjay) [Docker](https://hub.docker.com/r/casjay) 🤖  
⛵ CasjaysDevDocker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/r/casjaysdevdocker) ⛵  
