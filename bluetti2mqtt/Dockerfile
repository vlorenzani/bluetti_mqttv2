ARG BUILD_FROM
FROM $BUILD_FROM

# Copy data for add-on new 1
COPY rootfs /

# Install git dependencies for pip
RUN apt-get update && apt-get install -y --no-install-recommends \
    git \
    build-essential \
    python3-dev \
    libffi-dev \
    libssl-dev \
    cargo \
    bluez
    
# Install bluetti_mqtt
RUN pip install git+https://github.com/nhurman/bluetti_mqtt
RUN pip install pyasn1
RUN pip install cryptography 
RUN apk add --update --no-cache \
	 && apt-get clean \
	 && rm -rf /var/lib/apt/lists/*

	RUN chmod a+x /run.sh

CMD [ "/run.sh" ]
