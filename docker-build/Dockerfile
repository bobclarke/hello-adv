FROM alpine:latest

# Install nginx
RUN apk add --update nginx

# Config nginx
EXPOSE 80
COPY nginx.conf /etc/nginx/nginx.conf

CMD ["/usr/sbin/nginx", "-g", "daemon off;"]
