# Code-Server

## Why do I run this
This was a quick easy way to have a text editor without being SSH'd into my docker host constantly. I can donfigure my markdown documents, YML files etc all via a browser from anywhere in the world if I so choose. This is not currently publically available as I plan to do most things from home or on a VPN.

## My install
1. Make a directory for the code server to run from 
  ```
  mkdir code-server
  ```
2. Change to that directory  
   ```
  cd code-server
  ```
3. Run the docker command below. Please note the `<directory>` needs to be set where you want it to have access. Also be sure to remove or set a differnet password than whats in the example.
  ``` bash
  docker run -d \
    --name=code-server \
    -e PUID=1000 \
    -e PGID=1000 \
    -e TZ=Europe/London \
    -e PASSWORD=PasswordDUH `#optional` \ 
    -e HASHED_PASSWORD= `#optional` \
    -e SUDO_PASSWORD=password `#optional` \
    -e SUDO_PASSWORD_HASH= `#optional` \
    -e PROXY_DOMAIN=code.brantlab.com `#optional` \
    -p 8443:8443 \
    -v /home/docker/code:/config \
    -v '<directory>':'/config/<directory>':'rw'\
    --restart unless-stopped \
    ghc
  ```
Here is what I ran but yours may be different
  ``` bash
  docker run -d \
    --name=code-server \
    -e PUID=1000 \
    -e PGID=1000 \
    -e TZ=Europe/London \
    -e PASSWORD=PasswordDUH `#optional` \ 
    -e HASHED_PASSWORD= `#optional` \
    -e SUDO_PASSWORD=password `#optional` \
    -e SUDO_PASSWORD_HASH= `#optional` \
    -e PROXY_DOMAIN=code.brantlab.com `#optional` \
    -p 8443:8443 \
    -v /home/docker/code:/config \
    -v '/home/docker/':'/config/homer':'rw'\
    --restart unless-stopped \
    ghcr.io/linuxserver/code-server
  ```

## Source

[https://hub.docker.com/r/linuxserver/code-server](https://hub.docker.com/r/linuxserver/code-server4)