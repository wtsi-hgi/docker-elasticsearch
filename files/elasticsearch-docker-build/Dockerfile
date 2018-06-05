FROM docker.elastic.co/elasticsearch/elasticsearch-oss:6.2.4

ENV ELASTICSEARCH_INSTALL_DIRECTORY=/usr/share/elasticsearch
ENV STEAM_GUARD_VERSION=6.2.4-22.1

RUN "${ELASTICSEARCH_INSTALL_DIRECTORY}/bin/elasticsearch-plugin" install \
        -b "com.floragunn:search-guard-6:${STEAM_GUARD_VERSION}"

# Elasticsearch gets run by the entrypoint under the user "elasticsearch" (not configurable) - allowing that user to
# access root (config) files via root group permissions
RUN usermod -a -G root elasticsearch
