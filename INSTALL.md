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
wget https://download.elasticsearch.org/elasticsearch/elasticsearch/elasticsearch-0.90.3.deb
sudo dpkg -i elasticsearch-0.90.3.deb
sudo service elasticsearch start

3. Install and configure Logstash

TODO:
sudo mkdir —-parents /usr/local/bin/logstash
sudo cd /usr/local/bin/logstash
wget https://logstash.objects.dreamhost.com/release/logstash-1.2.1-flatjar.jar
cd ~
sudo mkdir —-parents /opt/logstashconfig
sudo java -jar /usr/local/bin/logstash/logstash.jar agent --config /opt/logstashconfig/redis2elasticsearch.conf -w 1 &
sudo java -jar /usr/local/bin/logstash/logstash.jar agent --config /opt/logstashconfig/logfile2redis.conf -w 2 &

5. install and configure nginx
TODO:
sudo apt-get install nginx
vim  /etc/nginx/sites-enabled/default
#change the default port 80 to 9000(optional)
sudo service nginx restart


6. Install and configure Kibana

TODO:
cd /usr/share/nginx/www/
sudo wget https://github.com/elasticsearch/kibana/archive/master.tar.gz
sudo tar -xvzf master.tar.gz
sudo mv kibana-master kibana






