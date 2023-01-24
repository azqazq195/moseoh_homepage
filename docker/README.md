docker stop $(docker ps -aq)
docker rm $(docker ps -aq)
docker rmi $(docker images -aq)

wget https://github.com/azqazq195/moseoh_homepage/archive/refs/heads/master.zip
unzip master.zip
mv moseoh_homepage-master/docker ./docker
rm -rf master.zip
rm -rf moseoh_homepage-master
cd docker
chmod +x init-letsencrypt.sh
./init-letsencrypt.sh
