FROM zammad/zammad-docker-compose:zammad
MAINTAINER Zammad <info@zammad.org>
ARG BUILD_DATE

LABEL org.label-schema.build-date="$BUILD_DATE" \
      org.label-schema.name="Zammad" \
      org.label-schema.license="AGPL-3.0" \
      org.label-schema.description="Docker container for Zammad - Rails server" \
      org.label-schema.url="https://zammad.org" \
      org.label-schema.vcs-url="https://github.com/zammad/zammad" \
      org.label-schema.vcs-type="Git" \
      org.label-schema.vendor="Zammad" \
      org.label-schema.schema-version="1.2" \
      org.label-schema.docker.cmd="sysctl -w vm.max_map_count=262144;docker-compose up"

# Expose ports
EXPOSE 3000

# docker init
COPY containers/zammad-railsserver/docker-entrypoint.sh /
RUN chown ${ZAMMAD_USER}:${ZAMMAD_USER} /docker-entrypoint.sh;chmod +x /docker-entrypoint.sh
ENTRYPOINT ["/docker-entrypoint.sh"]
CMD ["zammad-railsserver"]
