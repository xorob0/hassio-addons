ARG BUILD_FROM
FROM $BUILD_FROM

MAINTAINER Tim Simon <tim@mirahi.io>

# Set shell
SHELL ["/bin/bash", "-o", "pipefail", "-c"]

ENV LANG C.UTF-8

# Install requirements for add-on
RUN apk update && apk add --no-cache bash jq iw hostapd networkmanager net-tools sudo && rm -rf /var/cache/apk/*


COPY hostapd.conf /
COPY interfaces /etc/network/interfaces
COPY run.sh /
RUN chmod a+x /run.sh

CMD [ "/run.sh" ]
