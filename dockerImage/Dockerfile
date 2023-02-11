FROM pihole/pihole:latest
RUN apt update && apt install -y unbound \
    && rm -rf /var/lib/apt/lists/*

COPY pi-hole.conf /etc/unbound/unbound.conf.d/pi-hole.conf
COPY 99-edns.conf /etc/dnsmasq.d/99-edns.conf

RUN mkdir -p /etc/services.d/unbound
COPY run /etc/services.d/unbound/run

ENTRYPOINT ./s6-init

