FROM bitnami/minideb-extras:stretch-r163
LABEL maintainer "Bitnami <containers@bitnami.com>"

# Install required system packages and dependencies
RUN install_packages libbsd0 libc6 libgcc1 libstdc++6 libx11-6 libxau6 libxcb1 libxdmcp6
RUN bitnami-pkg unpack kibana-6.4.2-0 --checksum 037ab5b308fbb4e8c70f952b1bd86a20a1b687793e5d49b5c30b1257d499b3ec

COPY rootfs /
ENV BITNAMI_APP_NAME="kibana" \
    BITNAMI_IMAGE_VERSION="6.4.2-debian-9-r7" \
    KIBANA_ELASTICSEARCH_PORT_NUMBER="9200" \
    KIBANA_ELASTICSEARCH_URL="elasticsearch" \
    KIBANA_PORT_NUMBER="5601" \
    PATH="/opt/bitnami/kibana/bin:$PATH"

EXPOSE 5601

ENTRYPOINT [ "/app-entrypoint.sh" ]
CMD [ "nami", "start", "--foreground", "kibana" ]
