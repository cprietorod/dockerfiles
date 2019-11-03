SHELL=/bin/bash
version := $(shell echo "v"$(shell date "+%Y%m%d-%H%M" ))
#version := v20191102-2051

create_gcp:
	@echo "build "$(version)
	gcloud builds submit --timeout=30m  -t gcr.io/cprietorodriguez/my-cloud-sdk-docker:$(version) .

create_local:
	@echo "build "$(version)
	docker build -t cprietorod/my-cloud-sdk-docker:$(version) .
	
pull:
	@echo "pull from gcp "$(version)
	docker pull  gcr.io/cprietorodriguez/my-cloud-sdk-docker:$(version)

tag_gcp:
	@echo "tagging  "$(version)
	docker tag gcr.io/cprietorodriguez/my-cloud-sdk-docker:$(version)  cprietorod/my-cloud-sdk-docker:$(version)
	docker tag gcr.io/cprietorodriguez/my-cloud-sdk-docker:$(version)  cprietorod/my-cloud-sdk-docker:latest

tag_local:
	@echo "tagging  "$(version)
	docker tag cprietorod/my-cloud-sdk-docker:$(version)  cprietorod/my-cloud-sdk-docker:latest

push:
	@echo "push to docker "$(version)
	docker push cprietorod/my-cloud-sdk-docker:$(version)
	docker push cprietorod/my-cloud-sdk-docker:latest

build_gcp: create_gcp pull tag_gcp push

build_local: create_local tag_local push