# Config

## Edit docker-compose.yaml

Please edit the docker-compose.yaml to your liking.
For example you can change the server name, the port, the memory, etc.

NOTE: I'm opening the host to 0.0.0.0:25565 to the local network, you may want to change that.

## .env

```console
echo UID=$(id -u) > .env
echo GID=$(id -g) >> .env
```

Edit the dotenv file to add your whitelist and ops players.

```console
UID=501
GID=20
WHITELISTED_PLAYERS=mygamertag,player2,player3
OPS_PLAYERS=mygamertag
```

`Edit mods.txt to add your mods`

## Start Minecraft Server

```console
docker-compose up -d
```

### Follow the logs

```console
docker-compose logs -f minecraft-server
```

### Healthcheck

```console
docker exec -it minecraft-server mc-monitor status
```

## Minecraft Console

```
docker-compose exec minecraft-server rcon-cli
```

To list our whitelisted players:

```console
> /whitelist list
There are 3 whitelisted players: x, x, x
```

To restart the server:

```console
> /stop
```
