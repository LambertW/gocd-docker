FROM gocd/gocd-server:v17.8.0

COPY cruise-config.xml /go-working-dir/config/cruise-config.xml
COPY password.properties /go-working-dir/config/password.properties

RUN chown -R 1000 /go-working-dir

EXPOSE 8153
EXPOSE 8154