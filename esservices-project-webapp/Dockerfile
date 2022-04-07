# Get magnolia webapp
FROM alpine:3.12 AS builder
WORKDIR /app

COPY target/esservices-project-webapp-*.war /app/webapp.war
WORKDIR /app/
RUN unzip webapp.war && \
    rm -vf webapp.war

FROM busybox:latest AS final

COPY --from=builder /app/ /magnolia/
