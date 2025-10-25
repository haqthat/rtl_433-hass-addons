ARG BUILD_FROM=ghcr.io/home-assistant/amd64-base:3.19
FROM ${BUILD_FROM}

LABEL \
  io.hass.name="rtl_433 MQTT Auto Discovery (next) – custom" \
  io.hass.description="Publishes MQTT discovery for rtl_433 events (custom fork)" \
  io.hass.type="addon" \
  io.hass.version="local"

RUN apk add --no-cache python3 py3-pip curl && \
    pip3 install --no-cache-dir paho-mqtt

COPY run.sh /run.sh
COPY rtl_433_mqtt_hass.py /rtl_433_mqtt_hass.py
RUN chmod +x /run.sh

ENTRYPOINT ["/run.sh"]
