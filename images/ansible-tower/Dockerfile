FROM debian:stable

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update -qy \
 && apt-get upgrade -qy \
 && apt-get install -y \
    bridge-utils \
    iproute2 \
    python3-ipy \
    socat \
    screen \
    qemu-kvm \
    ssh \
    tcpdump \
    ethtool \
    telnet \
    procps \
 && rm -rf /var/lib/apt/lists/* \
 && mkdir tower

COPY rhel8.qcow2 /rhel8.qcow2
COPY license.txt /tower/license.txt
COPY tower.yml /tower/tower.yml
COPY launch.sh /

EXPOSE 22 161/udp 830 5000 10000-10099
ENTRYPOINT ["/launch.sh"]

