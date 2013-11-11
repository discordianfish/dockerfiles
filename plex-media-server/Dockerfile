from ubuntu:precise
maintainer Johannes 'fish' Ziemke <docker@freigeist.org>

run apt-get install -y -q wget libgcrypt11
run echo deb http://plex.r.worldssl.net/PlexMediaServer/ubuntu-repo lucid main >> /etc/apt/sources.list
run wget -O - http://plexapp.com/plex_pub_key.pub | apt-key add -
run apt-get update
run apt-get install -y -q plexmediaserver

env LD_LIBRARY_PATH /usr/lib/plexmediaserver
workdir /usr/lib/plexmediaserver
entrypoint [ "/usr/lib/plexmediaserver/Plex Media Server" ]
expose 32400:32400
