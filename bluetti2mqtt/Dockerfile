ARG BUILD_FROM
FROM $BUILD_FROM

# Copy data for add-on new 1
COPY rootfs /

# Install system dependencies using apt-get and clean up in the same layer
RUN apt-get update && apt-get install -y --no-install-recommends \
    git \
    build-essential \
    python3-dev \
    libffi-dev \
    libssl-dev \
    cargo \
    bluez \
 # Clean up apt cache to keep image smaller
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/*

# Install bluetti_mqtt and other pip packages
RUN pip install git+https://github.com/nhurman/bluetti_mqtt
RUN pip install pyasn1
RUN pip install cryptography 

# Set permissions for run script (Corrected indentation)
RUN chmod a+x /run.sh

CMD [ "/run.sh" ]
