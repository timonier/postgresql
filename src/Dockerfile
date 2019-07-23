FROM postgres:alpine

LABEL \
    maintainer="Morgan Auchede <morgan.auchede@gmail.com>"

RUN set -e -u -x \
\
    # Install packages
\
    && apk add --no-cache --no-progress --virtual BUILD_DEPS curl \
    && apk add --no-cache --no-progress bash ca-certificates \
\
    # Install dumb-entrypoint
\
    && curl --location "https://github.com/timonier/dumb-entrypoint/raw/master/src/dumb-entrypoint/installer" | bash -s -- install \
    && curl --location "https://github.com/timonier/dumb-entrypoint/raw/master/src/gosu/installer" | bash -s -- install \
\
    # Clean
\
    && apk del --no-progress BUILD_DEPS \
    && rm -f -r /tmp/*

COPY rootfs/ /

ENTRYPOINT [ "dumb-entrypoint" , "docker-entrypoint.sh" ]
