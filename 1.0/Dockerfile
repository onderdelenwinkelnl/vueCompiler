FROM alpine

LABEL Name="Fiyo" Version="1.0"

COPY script             /usr/local/bin/run-docker
COPY setup/init.sh      /tmp/setup-init.sh
COPY setup/vue.sh       /tmp/setup-vue.sh

RUN apk update --no-cache \
    && apk add --no-cache \
        util-linux \
        nodejs-npm \
        nodejs \
        screen \
        curl \
        bash \
        git

RUN /tmp/setup-init.sh
RUN /tmp/setup-vue.sh

WORKDIR /var/www

CMD [ "/usr/local/bin/run-docker", "-D", "FOREGROUND" ]