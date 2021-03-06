# spigot-docker
## Example docker-compose.yml

```
version: '3.2'
services:
  spigot:
    image: knieschraube/spigot
    restart: always
    ports:
      - 25565:25565
    environment:
      - SPIGOT_VER=latest
      - SPIGOT_EULA=true
    volumes:
      - spigot:/minecraft
      - ./my-plugins:/minecraft/plugins

volumes:
  spigot:
  ```

## Sending server commands
This project provides some basic tooling for sending server commands. 

### From Inside the Container:
The container comes with the `mcmd`-tool:
```
$ mcmd op knieschraube
```

### From the Host:
Included in this repository is the `mc.sh`-script which can be invoked from your compose-project:
```sh
$ cd /my-compose-projects/spigot-docker/
./mc.sh op knieschraube
```
