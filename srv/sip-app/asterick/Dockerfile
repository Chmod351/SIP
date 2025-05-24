# asterick/Dockerfile  (versión con paquetes binarios)
FROM ubuntu:22.04


RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends \
        asterisk  asterisk-mp3 iproute2 && \
    apt-get clean && rm -rf /var/lib/apt/lists/*


COPY config/ /etc/asterisk/

EXPOSE 5060/udp
EXPOSE 10000-20000/udp

ENTRYPOINT ["/usr/sbin/asterisk"]   # ← ruta absoluta que ya comprobaste

CMD ["-f", "-U", "root", "-vvv"]

