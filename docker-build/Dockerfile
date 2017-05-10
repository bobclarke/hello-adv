FROM alpine:latest

# Install nginx
RUN apk add --update nginx

# Config nginx
EXPOSE 80
COPY nginx.conf /etc/nginx/nginx.conf
COPY index.html /var/lib/nginx/html

CMD ["/usr/sbin/nginx", "-g", "daemon off;"]
