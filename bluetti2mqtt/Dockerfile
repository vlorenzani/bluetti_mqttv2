ARG BUILD_FROM
FROM $BUILD_FROM

# Copy data for add-on new 1
COPY rootfs /

# Install system dependencies using apk (Alpine package manager)
# Note: build-base is the Alpine equivalent of build-essential
# Note: openssl-dev is the Alpine equivalent of libssl-dev
# Note: Removing bluez version pin initially - add back if needed and available
RUN apk add --no-cache --force-overwrite \
    openssl=3.5.2-r0 \
    openssl-dev=3.5.2-r0 \
    libcrypto3=3.5.2-r0 \
    libssl3=3.5.2-r0

RUN apk add --no-cache \
    git \
    build-base \
    python3-dev \
    libffi-dev \
    cargo \
    bluez

# Install pip dependencies FIRST with explicit versions
RUN pip install --no-cache-dir --upgrade pip && \
    pip install --no-cache-dir \
	aiomqtt==2.1.0 \
        bleak==0.22.3 \
        crcmod==1.7 \
        cryptography==44.0.0 \
        dbus-next==0.2.3 \
        pyasn1==0.6.1 \
        pyserial==3.5 \
        prometheus_client==0.20.0

RUN pip install --no-cache-dir --no-deps git+https://github.com/vlorenzani/bluetti_mqtt.git

# Set permissions for run script
RUN chmod a+x /run.sh

RUN sed -i 's/sys.exit(main())/sys.exit(main(sys.argv))/' /usr/local/bin/bluetti-mqtt

# Optional: Clean apk cache if needed, though --no-cache minimizes it
# RUN rm -rf /var/cache/apk/*

CMD [ "/run.sh" ]