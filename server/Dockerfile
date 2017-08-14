FROM gocd/gocd-server:v17.8.0

# COPY Config into server setting directory
COPY cruise-config.xml /go-working-dir/config/cruise-config.xml
COPY password.properties /go-working-dir/config/password.properties

RUN chown -R 1000 /go-working-dir

HEALTHCHECK --interval=3m --timeout=5s --start-period=3m --retries=3 \
    CMD curl -f http://localhost:8153/go/ || exit 1

EXPOSE 8153
EXPOSE 8154