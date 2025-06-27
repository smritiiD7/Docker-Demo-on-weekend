FROM nginx:alpine

# Add labels
LABEL maintainer="Smriti"
LABEL description="Docker over weekends!"

# Copy custom NGINX config and HTML files
COPY nginx-conf/*.conf /etc/nginx/nginx.conf
COPY index-html-files/*.html /usr/share/nginx/html/

# Fix: install CA certs before any HTTPS call
#RUN apk update && apk add --no-cache ca-certificates bash

# Expose multiple ports
EXPOSE 8081 8082 8083
