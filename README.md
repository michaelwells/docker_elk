# ELK in docker demo

## Background
The Docker registry has official images for Elasticsearch, Logstash and Kibana now. I've put them together in a docker compose yaml file. Simply run docker-compose up from the repositories top directory.

This repo is just for demonstration and obviously isn't intended to be production ready. It is intended to expose the basics of docker-compose and highlight the availability of official images for the ELK stack

## Usage
```
docker-compose up
```
This should give you three containers, one for Elasticsearch, one for Logstash, and one for Kibana. To test this you can telnet to the Logstash TCP input (port 9876)
```
$ telnet localhost 9876
Trying 127.0.0.1...
Connected to localhost.
Escape character is '^]'.
Hello World!
Message 2
^]c

telnet> c
Connection closed.
```

Now hit your Kibana port (http://localhost:5601 unless you've changed it) and you should see your message(s). Feel free to push more messages into it as you feel necessary in order to prove that this is really working.

## Note
Docker-compose is not part of the docker distribution (yet), but instructions for installing it are [here](http://docs.docker.com/compose/install/)
