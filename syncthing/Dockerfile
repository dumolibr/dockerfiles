FROM ubuntu:trusty
# Dockerfile to run Syncthing. Requires an external container manager such as systemd to auto-restart the container when Syncthing restarts.
MAINTAINER Scott Hansen <firecat4153@gmail.com>

RUN useradd --no-create-home -g users -uid 22000 syncthing
ADD https://github.com/calmh/syncthing/releases/download/v0.9.4/syncthing-linux-amd64-v0.9.4.tar.gz /syncthing.tar.gz
RUN tar -xzvf syncthing.tar.gz && mv sync*/syncthing /syncthing && rm syncthing.tar.gz

USER syncthing
EXPOSE 8080 22000 21025/udp

CMD ["/syncthing", "-home=/config"]
