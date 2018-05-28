# Hello Ansible Docker Vagrant
A basic exmaple of using Varant, Ansible and Docker 

## pre requisites
- VirualBox 5.0.2 or above
- Vagrant 1.8.1 or above
- Ansible version 2.2.1.0 or above
- Git (any version should be fine)
- An internet connection :)


## How to run 
On the host OS, run the following commands:
- git clone https://github.com/bobclarke/hello-adv.git && cd hello-adv
- vagrant up

The resultant VirtualBox VM will have an IP address of 10.1.1.100 and a hostname of jupiter. 
(This, along with memory an vcpu count can be changed by editing VagrantFile)

Once the build has finished, Nginx will be available to the host OS at http://10.1.1.100:80 and Tomcat will be available at http://10.1.1.100:8888.

The manager credetials for Tomcat are admin/admin








