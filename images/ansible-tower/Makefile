# SHELL=/bin/bash

TARGET_VERSION ?= latest

all: docker

docker:
	gsutil cp "gs://nrelabs-curriculum-base-images/redhat/license_118ae85ee51e4b249209a8c03b587517.txt" "./license.txt"
        gsutil cp "gs://nrelabs-curriculum-base-images/redhat/rhel-8.0-update-3-x86_64-kvm.qcow2" "./rhel8.qcow2"
        gsutil cp "gs://nrelabs-curriculum-base-images/redhat/tower.yml" "./tower.yml"
	docker build --pull --no-cache -t cloudtoad/ansible-tower:$(TARGET_VERSION) .
	docker push cloudtoad/ansible-tower:$(TARGET_VERSION)

