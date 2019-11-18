xteve
xteve, in docker with ovpn

docker runs in host mode
access xteve webui ip:34400/web/

mounts to use as sample
Container Path: /root/.xteve <> /mnt/user/appdata/xteve/
Container Path: /tmp/xteve <> /tmp/xteve/
while /mnt/user/appdata/ should fit to your system path ...

docker run -d \
  --name=xteve \
  --net=host \
  --log-opt max-size=10m \
  --log-opt max-file=3 \
  -e TZ="Europe/Berlin" \
  -v /mnt/user/appdata/xteve/:/root/.xteve:rw \
  -v /tmp/xteve/:/tmp/xteve:rw \
  alturismo/xteve_vpn

xteve - iptv and epg proxy server for plex, emby, etc ... thanks to @marmei
website: http://xteve.de
Discord: https://discordapp.com/channels/465222357754314767/465222357754314773

so, credits to the programmers, i just putted this together in a docker to fit my needs
