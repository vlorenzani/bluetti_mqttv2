ARG BUILD_FROM
FROM $BUILD_FROM

# Copy data for add-on new 1
COPY rootfs /

# Install git dependencies for pip
RUN apk add --no-cache \
    git \
    build-base \
    python3-dev \
    musl-dev \
    libffi-dev \
    openssl-dev \
    cargo
    
# Install bluetti_mqtt
RUN pip install git+https://github.com/nhurman/bluetti_mqtt
RUN pip install pyasn1
RUN pip install cryptography 
RUN apk add --update --no-cache \
	bluez=5.65-r0 \
	&& rm -rf /var/cache/apk/* /lib/apk/db/* \
	&& chmod a+x /run.sh

CMD [ "/run.sh" ]
