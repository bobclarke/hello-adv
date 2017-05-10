FROM alpine:latest


# Install openrc
RUN  apk update && apk add openrc

# Tell openrc that its running inside a container
RUN sed -i 's/#rc_sys=""/rc_sys="lxc"/g' /etc/rc.conf

# Config openrc so it knows loopback and net are already there
RUN echo 'rc_provide="loopback net"' >> /etc/rc.conf

# Disable loggers
RUN sed -i 's/^#\(rc_logger="YES"\)$/\1/' /etc/rc.conf

# Disable tty's as we're not in privileged mode
RUN sed -i '/tty/d' /etc/inittab

# No need to swet the hostname as docker handles this 
RUN sed -i 's/hostname $opts/# hostname $opts/g' /etc/init.d/hostname

# We can't mount tmpfs since not privileged
RUN sed -i 's/mount -t tmpfs/# mount -t tmpfs/g' /lib/rc/sh/init.sh

# can't do cgroups
RUN sed -i 's/cgroup_add_service /# cgroup_add_service /g' /lib/rc/sh/openrc-run.sh

# clean apk cache
RUN rm -rf /var/cache/apk/*

# Install nginx
RUN apk add --update nginx

# Config nginx
EXPOSE 80
COPY nginx.conf /etc/nginx/nginx.conf

#CMD ["/sbin/init"]
CMD ["/usr/sbin/nginx"]
