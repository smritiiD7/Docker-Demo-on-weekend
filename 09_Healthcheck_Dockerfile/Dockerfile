FROM nginx:alpine


LABEL Name="Smriti"
LABEL Description="Demonstrates about HEALTHCHECK Command"

RUN apk --no-cache add curl

COPY index.html /usr/share/nginx/html

#HEALTHCHECK --interval=30s --timeout=30s --start-period=5s --retries=3 CMD curl -f http://localhost/ || exit 1
HEALTHCHECK --interval=30s --timeout=30s --start-period=5s --retries=3  \
CMD curl -f http://localhost/ || exit 1
