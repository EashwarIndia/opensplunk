Installation guide
=========

We track all instructions for installation here.

Later we will simplify or automate them, by bash or puppet. 

Then move the instruction to "Quick start" section of README.md.


sudo apt-get update
sudo apt-get upgrade
sudo apt-get install default-jre -y


1. Install and configure Redis

TODO:
sudo apt-get install redis-server
sudo service redis status

2. Install and configure ElasticSearch

TODO:
sudo mkdir --parents /usr/local/feng
sudo wget https://download.elasticsearch.org/elasticsearch/elasticsearch/elasticsearch-0.90.3.deb
sudo dpkg -i elasticsearch-0.90.3.deb
sudo service elasticsearch start

3. Install and configure Logstash

TODO:
sudo mkdir --parents /usr/local/feng/bin/logstash
sudo cd /usr/local/feng/bin/logstash
sudo wget https://logstash.objects.dreamhost.com/release/logstash-1.2.1-flatjar.jar
sudo mv logstash-1.2.1-flatjar.jar  logstash.jar
sudo mkdir --parents /usr/local/feng/config/logstash

5. install and configure nginx
TODO:
sudo apt-get install nginx
sudo vim  /etc/nginx/sites-enabled/default
#manually change the default port 80 to 9000(optional) or sed  -i /#listen  80;/  listen   9000; /
sudo service nginx restart

6. start logstash

sudo java -jar /usr/local/feng/bin/logstash/logstash.jar agent --config /usr/local/feng/config/logstash/redis2elasticsearch.conf -w 1 &
sudo java -jar /usr/local/feng/bin/logstash/logstash.jar agent --config /usr/local/feng/config/logstash/logfile2redis.conf -w 2 &

7. Install and configure Kibana

TODO:
cd /usr/share/nginx/www/
sudo wget https://github.com/elasticsearch/kibana/archive/master.tar.gz
sudo tar -xvzf master.tar.gz
sudo mv kibana-master kibana






