Installation guide
=========

We track all instructions for installation here.

Later we will simplify or automate them, by bash or puppet. 

Then move the instruction to "Quick start" section of README.md.

=========

https://github.com/stephendotexe/Logstash_kibana_auto_install/archive/master.zip

Downlaod above project, But have to make some changes to the config files and the bash file. 

vim default/elasticsearch
MAX_OPEN_FILES=65535  << change this to MAX_OPEN_FILES=1024  (approx 300 files for 1Gigs of RAM)
Comment the 7th line, the server is not dedicated to logservice (ElasticSearch will not start if 50% of memory is not available)

vim logstash_server
apt-get install git-core  << add this line to the code
sed -i 's#KibanaPort =.*#KibanaPort = 80#' KibanaConfig.rb  (45th line)  << specify the port for kibana .Default it is 80 in this puppet script

Now run the bash file
./logstash_server




1. Install and configure Redis

TODO:

2. Install and configure Logstash

TODO:

3. Install and configure ElasticSearch

TODO:

3. Install and configure Kibana

TODO:

