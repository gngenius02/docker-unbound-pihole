FROM pihole/pihole:latest
RUN apt update && apt install -y unbound \
    && rm -rf /var/lib/apt/lists/*

COPY unbound-pihole.conf /etc/unbound/unbound.conf.d/pi-hole.conf
COPY 99-edns.conf /etc/dnsmasq.d/99-edns.conf
RUN mkdir -p /etc/services.d/unbound
COPY unbound-run /etc/services.d/unbound/run

RUN mkdir -p /var/log/unbound
RUN chown -R unbound:unbound /var/log/unbound

ENTRYPOINT ./s6-init

