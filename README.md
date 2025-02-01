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
      - /srv/dev-disk-by-uuid-..../downloads/config/qbittorent:/config
      - /srv/dev-disk-by-uuid-..../downloads:/downloads
    ports:
      - 8080:8080
      - 6881:6881
      - 6881:6881/udp
    restart: unless-stopped
```
Путь можно посмотреть в web ui OVM или же ls /srv и выбрать нужный диск
