GIT_TAG := $(shell git rev-parse --short HEAD)

all: build tag push

build:
	docker build -t curso_gocd_ep_6:$(GIT_TAG) .

tag:
	docker tag curso_gocd_ep_6:$(GIT_TAG) 972777588758.dkr.ecr.eu-west-1.amazonaws.com/curso_gocd_ep_6:$(GIT_TAG)
	docker tag curso_gocd_ep_6:$(GIT_TAG) 972777588758.dkr.ecr.eu-west-1.amazonaws.com/curso_gocd_ep_6:latest

push:
	aws ecr get-login --no-include-email --region eu-west-1|sh && docker push 972777588758.dkr.ecr.eu-west-1.amazonaws.com/curso_gocd_ep_6:latest && docker push 972777588758.dkr.ecr.eu-west-1.amazonaws.com/curso_gocd_ep_6:$(GIT_TAG)


test:
	docker run -d -p 8080:80 --rm --name curso_gocd_ep_6 curso_gocd_ep_6:$(GIT_TAG)
	sleep 2
	curl localhost:8080

test_clean:
	docker rm -f curso_gocd_ep_6
