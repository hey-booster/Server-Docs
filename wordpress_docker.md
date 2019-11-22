### Install Wordpress with Docker

sudo su app
cd ../app

**If new vm**

sudo fallocate -l 4G /swapfile
sudo chmod 600 /swapfile 
sudo mkswap /swapfile
sudo swapon /swapfile
sudo vim /etc/fstab --> /swapfile none swap sw 0 0

---

curl https://get.docker.com > install-docker.sh
chmod 755 install-docker.sh
sudo ./install-docker.sh 
sudo usermod -aG docker app
exit -> login

---

sudo curl -L "https://github.com/docker/compose/releases/download/1.24.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod 755 /usr/local/bin/docker-compose

git clone https://github.com/chrisbmatthews/wordpress-docker-compose.git
docker-compose up -d
