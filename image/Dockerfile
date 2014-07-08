FROM ubuntu:12.04
MAINTAINER Devinder Khroad <dkhroad@gmail.com>

ENV HOME /root
RUN mkdir /build
ADD . /build

RUN /build/prepare.sh && \
	/build/system_services.sh && \
	/build/utilities.sh && \
	/build/cleanup.sh

# Install init script to add SSH keys
# Based on https://github.com/rfkrocktk/docker-baseimage
RUN chmod +x /etc/my_init.d/01_add_ssh_keys.sh

CMD ["/sbin/my_init"]
