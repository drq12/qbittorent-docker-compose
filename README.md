# qbittorent-docker-compose
qbittorent, docker-compose, openmediavault

```
---
services:
  qbittorrent:
    image: lscr.io/linuxserver/qbittorrent:latest
    container_name: qbittorrent
    environment:
      - PUID=1000
      - PGID=1000
      - TZ=Etc/UTC
      - WEBUI_PORT=8080
      - TORRENTING_PORT=6881
      - UMASK=000
    volumes:
      - /srv/dev-disk-by-uuid-..../downloads/config/:/config
      - /srv/dev-disk-by-uuid-..../downloads:/downloads
    ports:
      - 8080:8080
      - 6881:6881
      - 6881:6881/udp
    restart: unless-stopped
```
Путь можно посмотреть в web ui OVM или же ls /srv и выбрать нужный диск
user/pass будут видны в логах в момент запуска, посмотреть можно через веб интерфейс OVM, или через консоль 

```
docker ps
docker logs id-qtbittorent-container
```

```
******** Information ********
To control qBittorrent, access the WebUI at: http://localhost:8080
The WebUI administrator username is: admin
The WebUI administrator password was not set. A temporary password is provided for this session: *********
You should set your own password in program preferences.
```
