IMAGE_NAME := $(shell git rev-parse --short HEAD)

build_and_tag: build tag

build:
	docker build -t curso_gocd_ep_6:$(IMAGE_NAME) .

tag:
	docker tag curso_gocd_ep_6:$(IMAGE_NAME) curso_gocd_ep_6:latest
