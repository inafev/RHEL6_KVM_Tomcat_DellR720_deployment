# Red Hat Enterprise Linux 6 remote deployment on Dell PowerEdge R720 & KVM virtualization with qcow2 pre-allocation (2012)

- Document Title: Best practices, recommendations and notes: Red Hat Enterprise Linux 6.3 remote installation/deployment on DELL PowerEdge R720 (12G), KVM hypervisor, Tomcat7, Uptime &amp; Performance Tips.
- [This document in HTML format rendered with rawgit] (https://rawgit.com/inafev/RHEL6_KVM_Tomcat_DellR720_deployment/master/RHEL6_KVM_Tomcat_DellR720_deployment.html)  
- [The URL reference document in HTML format rendered with rawgit](https://rawgit.com/inafev/RHEL6_KVM_Tomcat_DellR720_deployment/master/URL%20references.html)
- [The evernote online version of this document](http://bit.ly/Ulb98Q )

### Table of contents
1. Remote Deployment Procedure of RHEL6.3 x86_64 on Dell PowerEdge R720
2. KVM Hypervisor (‘Virtual Host’) with VMs for WebApp on local storage
3. DELL USC
4. BIOS Boot partitioning
5. Importance of detaching VG data from VG system (LVM2) on hypervisors and VMs
6. DELL PowerEdge firmware update via YUM
7. Macvtap
8. qcow2 pre-allocation
9. performance analysis script
10. network latency analysis
11. load testing with JMeter HTTP
12. Java Garbage Collector ulimit & tuning
13. sudo and Upstart scripts for Apache and Tomcat
14. Importance of ports > 1024 no root for balanced Apaches
15. NTP
16. libvirt-snmp zenoss
17. KVM’s virsh CLI
18. rsync (solaris to linux migration), alternatives to portal/CMS Microsoft Sharepoint, etc.


## New reference list updated, December 2015:
- [How to Install RedHat Enterprise Virtualization (RHEV) 3.5] (http://www.tecmint.com/install-redhat-virtualization-rhev/)
- [How to Create Virtual Machines in Linux Using KVM (Kernel-based Virtual Machine)] (http://www.tecmint.com/install-and-configure-kvm-in-linux/)
- [Open source Virtualization by Quru, the fastest-growing Red Hat solution provider based in London](https://youtu.be/F2lxJTdfVy8)
- [Improve your development environments with virtualization](http://pyvideo.org/video/3411/improve-your-development-environments-with-virtua)
- [JBoss Data Virtualization 6.1](http://www.ossmentor.com/2015/04/data-virtualization-61-getting-started.html)
- [FOSS Network Functions Virtualization](https://www.opnfv.org) 
- [Free eBook - Docker Security: Using Containers Safely in Production](https://www.openshift.com/promotions/docker-security.html)
- [Why docker](http://www.javacodegeeks.com/2015/11/why-docker.html)
- [Getting started with docker](https://dzone.com/refcardz/getting-started-with-docker-1)
- [Deploying Containers with Docker Swarm and Docker Networking](http://www.javacodegeeks.com/2015/11/deploying-containers-docker-swarm-docker-networking.html)
- [Docker for the python developer, podcast at http://talkpython.fm/](http://talkpython.fm/episodes/show/9/docker-for-the-python-developer)
- [How to be Successful Running Docker in Production](http://www.infoq.com/news/2015/11/running-docker-production)
- [Monitoring Docker: Part II](http://blog.logscape.com/2014/07/monitoring-docker-part-ii/)
- [Gathering LXC and Docker containers metrics](http://blog.docker.com/2013/10/gathering-lxc-docker-containers-metrics/)
- [Red Hat containers](http://www.redhat.com/en/insights/containers)
- [10 Awesome Docker Tutorials to Kick-Start your DevOps Projects](http://www.javacodegeeks.com/2015/11/10-awesome-docker-tutorials-to-kick-start-your-devops-projects.html)
- [Docker cookbook](http://shop.oreilly.com/product/0636920036791.do?sortby=publicationDate)
- [How Vagrant Eases the Software Research and Testing - The New Stack](http://thenewstack.io/vagrant-developers-researchers/)
- [Learning Puppet with Vagrant, video tutorial at sysadmincasts.com](http://sysadmincasts.com/episodes/8-learning-puppet-with-vagrant)
- [7 Open Source tools for java deployment:Jenkins, Chef, Vagrant, Packer, Docker, Flyway, Rundeck, Go](http://www.oraclejavamagazine-digital.com/javamagazine_twitter/20140506?pg=6#pg6)
- [Why tools like Docker, Vagrant, and Ansible are hotter than ever](http://opensource.com/business/15/5/why-Docker-Vagrant-and-Ansible)
- [A book on Ansible by Jeff Geerling](http://www.ansiblefordevops.com/)
- [Ansible examples from Ansible for DevOps - github code](https://github.com/geerlingguy/ansible-for-devops)
- [How to Install and Configure ‘Ansible’ Automation Tool for IT Management](http://www.tecmint.com/install-and-configure-ansible-automation-tool-in-linux/)
- [Ansible video tutorial at sysadmincasts.com](https://sysadmincasts.com/episodes/43-19-minutes-with-ansible-part-1-4)
- [Crash course on Vagrant, video tutorial at sysadmincasts.com](https://sysadmincasts.com/episodes/42-crash-course-on-vagrant-revised)
