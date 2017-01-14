.PHONY: build run stop start

IMAGE_NAME = sruml/postgres
CONTAINER_NAME = postgres
TAG = 1.0.0

build:
	docker build -t ${IMAGE_NAME}:${TAG} .

run:
	docker run -d -p 5432:5432 -v /usr/local/docker/postgresql:/var/lib/postgresql -e POSTGRES_PASSWORD=postgres --name ${CONTAINER_NAME} ${IMAGE_NAME}:${TAG}

stop:
	docker stop ${CONTAINER_NAME}

start:
	docker start ${CONTAINER_NAME}

volume:
	sudo mkdir -p /usr/local/docker/postgresql

psql:
	docker exec -it ${CONTAINER_NAME} psql -U postgres
