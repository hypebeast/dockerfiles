.PHONY: build run stop start

IMAGE_NAME = sruml/mysql
CONTAINER_NAME = mysql
TAG = 1.0.0
ROOT_PASSWORD = mysql

build:
	docker build -t ${IMAGE_NAME}:${TAG} .

run:
	docker run -d \
		-p 3306:3306 \
		-v /usr/local/docker/mysql:/var/lib/mysql \
		-e MYSQL_ROOT_PASSWORD=${ROOT_PASSWORD} \
		--name ${CONTAINER_NAME} \
		${IMAGE_NAME}:${TAG}

stop:
	docker stop ${CONTAINER_NAME}

start:
	docker start ${CONTAINER_NAME}

volume:
	sudo mkdir -p /usr/local/docker/mysql

connect:
	docker exec -it ${CONTAINER_NAME} mysql -uroot -p${ROOT_PASSWORD}

rm:
	docker rm ${CONTAINER_NAME}

logs:
	docker logs ${CONTAINER_NAME}
