.PHONY: pg-up es-up mem-up mq-up all-up

pg-up:
	docker run --name some-postgres -e POSTGRES_PASSWORD=mysecretpassword -d postgres

es-up:
	docker run --name some-elasticsearch -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" -d docker.elastic.co/elasticsearch/elasticsearch:9.5.5

mem-up:
	docker run --name some-memcached -p 11211:11211 -d memcached:alpine

mq-up:
	docker run --name some-rabbitmq -p 5672:5672 -p 15672:15672 -d rabbitmq:3-management

all-up: pg-up es-up mem-up mq-up

halt:
	docker stop some-postgres some-elasticsearch some-memcached some-rabbitmq