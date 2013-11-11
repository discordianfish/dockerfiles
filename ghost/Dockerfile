from base
maintainer Johannes 'fish' Ziemke <docker@freigeist.org>
workdir /srv
expose 8080

run echo "force-unsafe-io" > /etc/dpkg/dpkg.cfg.d/02apt-speedup
run echo "Acquire::http {No-Cache=True;};" > /etc/apt/apt.conf.d/no-cache
run echo 'deb http://archive.ubuntu.com/ubuntu quantal main universe' >> /etc/apt/sources.list
run echo 'deb http://ppa.launchpad.net/chris-lea/node.js/ubuntu quantal main' >> /etc/apt/sources.list
run apt-key adv --keyserver keyserver.ubuntu.com --recv-keys C7917B12
run apt-get update
run apt-get install -y -q nodejs curl unzip
run curl -LO http://ghost.org/zip/ghost-0.3.3.zip && unzip ghost-0.3.3.zip && rm ghost-0.3.3.zip
run npm install --production
add config.js /srv/

cmd [ "npm", "start" ]
env NODE_ENV production
