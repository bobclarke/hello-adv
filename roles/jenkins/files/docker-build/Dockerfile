FROM jenkins:latest

RUN mkdir -p /tmp/jenkins/docker-build && \
    mkdir -p /var/jenkins_home/jobs/myjob

ADD config.xml /var/jenkins_home
ADD scriptApproval.xml /var/jenkins_home
ADD job.xml /var/jenkins_home/jobs/myjob/config.xml
ADD plugins.txt /tmp/jenkins/docker-build/
ADD create-admin-account.groovy /usr/share/jenkins/ref/init.groovy.d/

RUN rm -rf /usr/share/jenkins/ref/plugins/*.lock
RUN /usr/local/bin/install-plugins.sh `echo $(cat /tmp/jenkins/docker-build/plugins.txt)`
