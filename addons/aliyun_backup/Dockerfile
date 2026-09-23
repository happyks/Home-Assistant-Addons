# https://developers.home-assistant.io/docs/add-ons/configuration#add-on-dockerfile
ARG BUILD_FROM
FROM $BUILD_FROM

# Execute during the build of the image
ARG TEMPIO_VERSION BUILD_ARCH

RUN \
    apk add python3 py3-pip git curl

RUN \
    python3 -m pip install --upgrade pip --break-system-packages \
    && python3 -m pip install --upgrade Pillow --break-system-packages \
    && python3 -m pip install --upgrade schedule --break-system-packages \
    && python3 -m pip install --upgrade pytz --break-system-packages \
    && python3 -m pip install --upgrade python-dateutil --break-system-packages \
    && pip install -U aligo --break-system-packages \
    && pip install git+https://github.com/foyoux/aligo.git --break-system-packages

# Copy root filesystem
COPY rootfs /
