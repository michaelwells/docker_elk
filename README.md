# ELK in docker demo

## Background
The Docker registry has official images for Elasticsearch and Logstash now. If you combine these with a kibana image you can get the full ELK stack running locally very easily. I've put them together in a docker compose yaml file. Simply run docker-compose up from the repositories top directory.

This repo is just for demonstration and obviously isn't intended to be production ready. It is intended to expose the basics of docker-compose and highlight the availablity of official images for both elasticsearch and logstash.

## Usage
```
docker-compose up
```
This should give you three containers, one for Elasticsearch, one for Logstash, and one for Kibana. To test this use docker exec to put something in the /var/log/messages
```
docker exec -it dockerelk_logstash_1 bash -c "/bin/echo test >> /var/log/messages"
```

Now hit your kibana port (http://localhost:5601 unless you've changed it) and you should see your message(s). Feel free to push more messages into it as you feel necessary in order to prove that this is really working.

## Note
Docker-compose is not part of the docker distribution (yet), but instructions for installing it are [here](http://docs.docker.com/compose/install/)
