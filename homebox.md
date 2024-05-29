chown 65532:65532 -R /home/35services/Documents/homebox
docker run -d \
  --name homebox \
  --restart unless-stopped \
  --publish 3100:7745 \
  --env TZ=Europe/Bucharest \
  --volume /home/35services/Documents/homebox:/data \
  ghcr.io/hay-kot/homebox:latest
