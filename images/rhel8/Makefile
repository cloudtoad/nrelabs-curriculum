# SHELL=/bin/bash

TARGET_VERSION ?= latest

all: docker

docker:
	gsutil cp "gs://nrelabs-curriculum-base-images/rhel-8.0-update-3-x86_64-kvm.qcow2" "./rhel8.qcow2"
	docker build --pull --no-cache -t cloudtoad/rhel8:$(TARGET_VERSION) .
	docker push cloudtoad/rhel8:$(TARGET_VERSION)

