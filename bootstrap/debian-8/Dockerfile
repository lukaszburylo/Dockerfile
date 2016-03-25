FROM debian:8
MAINTAINER lukasz@burylo.com

ENV LANG       en_US.UTF-8
ENV LC_ALL     en_US.UTF-8
#
# # Add common scripts (from _localscripts)
ADD scripts.tar /
#
# # Init bootstrap (and install ansible)
RUN export DEBIAN_FRONTEND=noninteractive \
    && set -x \
    # Fix root terminal
    && echo "export TERM=xterm" >> /root/.bashrc \
    # System update
    && apt-get update \
    && apt-get upgrade -y \
    # Base stuff
    && apt-get install -y \
    lsb-release \
    ca-certificates \
    # Generate locales
    locales-all 
