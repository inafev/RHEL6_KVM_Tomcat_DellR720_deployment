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


# New reference list updated, December 2015
## Red Hat virtualization
- [How to Install RedHat Enterprise Virtualization (RHEV) 3.5] (http://www.tecmint.com/install-redhat-virtualization-rhev/)
- [How to Create Virtual Machines in Linux Using KVM (Kernel-based Virtual Machine)] (http://www.tecmint.com/install-and-configure-kvm-in-linux/)
- [Open source Virtualization by Quru, the fastest-growing Red Hat solution provider based in London](https://youtu.be/F2lxJTdfVy8)

## Microservices
- [Introduction to Microservices | NGINX](https://www.nginx.com/blog/introduction-to-microservices/)
- [What are Microservices?](https://www.linkedin.com/pulse/what-microservices-walli-datoo)
- [Microservices architecture: advantages and drawbacks](http://cloudacademy.com/blog/microservices-architecture-challenge-advantage-drawback/)

## Nginx
- [How to Setup Name-based and IP-based Virtual Hosts (Server Blocks) with NGINX](http://www.tecmint.com/nginx-name-based-and-ip-based-virtual-hosts-server-blocks/)

## Data virtualization
- [JBoss Data Virtualization 6.1](http://www.ossmentor.com/2015/04/data-virtualization-61-getting-started.html)

## Network virtualization
- [FOSS Network Functions Virtualization](https://www.opnfv.org) 

## Docker
- [Adoption/popularity is the new king. The only constant is change! - puppet, chef, ansible, docker ](http://getcloudify.org/2015/10/21/configuration-management-chef-puppet-ansible-emc-dell-vmware-orchestration.html)
- [DockerCon EU: Software Testing with Docker](http://thenewstack.io/software-testing-docker/)
- [Free eBook - Docker Security: Using Containers Safely in Production](https://www.openshift.com/promotions/docker-security.html)
- [Why docker](http://www.javacodegeeks.com/2015/11/why-docker.html)
- [Getting started with docker](https://dzone.com/refcardz/getting-started-with-docker-1)
- [Deploying Containers with Docker Swarm and Docker Networking](http://www.javacodegeeks.com/2015/11/deploying-containers-docker-swarm-docker-networking.html)
- [Docker for the python developer, podcast at http://talkpython.fm/](http://talkpython.fm/episodes/show/9/docker-for-the-python-developer)
- [How to be Successful Running Docker in Production](http://www.infoq.com/news/2015/11/running-docker-production)
- [Monitoring Docker: Part II](http://blog.logscape.com/2014/07/monitoring-docker-part-ii/)
- [Gathering LXC and Docker containers metrics](http://blog.docker.com/2013/10/gathering-lxc-docker-containers-metrics/)
- [Red Hat containers](http://www.redhat.com/en/insights/containers)
- [Red Hat loves containers in RHEL 7.2](http://www.zdnet.com/article/red-hat-loves-containers-in-rhel-7-2/)
- [Taste of Red Hat Training: Customizing a container to deploy a network service](http://www.redhat.com/en/about/videos/taste-red-hat-training-customizing-container-deploy-network-service)
- [Red Hat Drives Networking, Linux Container Innovation in Latest Version of Red Hat Enterprise Linux 7](http://www.redhat.com/en/about/press-releases/red-hat-drives-networking-linux-container-innovation-latest-version-red-hat-enterprise-linux-7)
- [Architecting Containers Part 1: Why Understanding User Space vs. Kernel Space Matters](http://rhelblog.redhat.com/2015/07/29/architecting-containers-part-1-user-space-vs-kernel-space/)
- [​CoreOS brings end-to-end trusted computing to containers](http://www.zdnet.com/article/coreos-brings-end-to-end-trusted-computing-to-containers/)
- [10 Awesome Docker Tutorials to Kick-Start your DevOps Projects](http://www.javacodegeeks.com/2015/11/10-awesome-docker-tutorials-to-kick-start-your-devops-projects.html)
- [Docker cookbook](http://shop.oreilly.com/product/0636920036791.do?sortby=publicationDate)

### Configuration Management, Vagrant
- [Learning Puppet with Vagrant, video tutorial at sysadmincasts.com](http://sysadmincasts.com/episodes/8-learning-puppet-with-vagrant)
- [7 Open Source tools for java deployment:Jenkins, Chef, Vagrant, Packer, Docker, Flyway, Rundeck, Go](http://www.oraclejavamagazine-digital.com/javamagazine_twitter/20140506?pg=6#pg6)
- [How Vagrant Eases the Software Research and Testing - The New Stack](http://thenewstack.io/vagrant-developers-researchers/)
- [Improve your development environments with virtualization - Vagrant, Python ](http://pyvideo.org/video/3411/improve-your-development-environments-with-virtua)
- [Why tools like Docker, Vagrant, and Ansible are hotter than ever](http://opensource.com/business/15/5/why-Docker-Vagrant-and-Ansible)
- [Crash course on Vagrant, video tutorial at sysadmincasts.com](https://sysadmincasts.com/episodes/42-crash-course-on-vagrant-revised)

### Configuration Management, Ansible
- [Demo: Chef vs Puppet vs Ansible](https://www.youtube.com/watch?v=miO00M4vPok)
- [Are Docker Users Migrating to Ansible and Away from Puppet and Chef?](http://thenewstack.io/are-docker-users-migrating-to-ansible-and-away-from-puppet-and-chef/)
- [Ansible, Just Use It - slide](https://speakerdeck.com/vranac/ansible-just-use-it)
- [Ansible playbook to provision a WebLogic Fusion Middleware Domain on RHEL/CentOS 7](http://unversioned.blogspot.gr/2015/10/ansible-playbook-provision-weblogic-fusion-middleware-12.1.3-centos-7.html)
- [Ansible vs Puppet – Hands-On with Ansible](https://dantehranian.wordpress.com/2015/01/20/ansible-vs-puppet-hands-on-with-ansible/)
- [Ansible for DevOps, a book on Ansible by Jeff Geerling](http://www.ansiblefordevops.com/)
- [Ansible examples from Ansible for DevOps - github code](https://github.com/geerlingguy/ansible-for-devops)
- [How to Install and Configure ‘Ansible’ Automation Tool for IT Management](http://www.tecmint.com/install-and-configure-ansible-automation-tool-in-linux/)
- [Ansible video tutorial at sysadmincasts.com](https://sysadmincasts.com/episodes/43-19-minutes-with-ansible-part-1-4)

### Configuration Management, Puppet
- [Github: The Puppet Dashboard is a web interface providing node classification and reporting features for Puppet, an open source system configuration management tool](https://github.com/sodabrew/puppet-dashboard)
- [Github: Smarter Puppet deployment.R10k provides a general purpose toolset for deploying Puppet environments and modules](https://github.com/puppetlabs/r10k)
- [Librarian-puppet is a bundler for your puppet infrastructure. You can use librarian-puppet to manage the puppet modules your infrastructure depends on, whether the modules come from the Puppet Forge, Git repositories or a just a path](http://librarian-puppet.com/)
- [puppetlabs/mcollective](https://forge.puppetlabs.com/puppetlabs/mcollective)
- [Puppet and Python](http://pyvideo.org/video/3649/puppet-and-python)
- [Puppet Modules: Apps for Ops](http://pyvideo.org/video/2589/puppet-modules-apps-for-ops)
- [Sysadmincasts.com: Git to Puppet Deployment Workflow](https://sysadmincasts.com/episodes/33-git-to-puppet-deployment-workflow)
- [Podcast: Docker & Puppet: Uniting Containers with Configuration Management](https://puppetlabs.com/podcasts/podcast-docker-puppet-combining-containers-configuration-management)
- [Webinar: Getting Started with Puppet Enterprise 3.3](https://puppetlabs.com/webinars/getting-started-puppet-enterprise-33-us)
- [Puppet Enterprise 3.3 disponible con soporte para RHEL 7, Ubuntu 14.04 LTS, Windows Server 2012 R2, y Mac OS X Mavericks](https://puppetlabs.com/blog/puppet-enterprise-3.3-get-started-faster)
- [Sysadmincasts.com: Learning Puppet with Vagrant](https://sysadmincasts.com/episodes/8-learning-puppet-with-vagrant)
- [Twitter's transition from Puppet to Ansible](https://www.youtube.com/watch?v=fwGrKXzocg4)
- [Learning Puppet can be like drinking from a fire hose. Here is a guide to basic terms and resources to help you learn](https://puppetlabs.com/blog/starting-puppet-basics-from-puppet-labs-employee)
- [Geppetto, eclipse plugin for puppet](https://puppetlabs.com/blog-tags/geppetto)

### Jenkins
- [Jenkins User Conference West 2015 - Slides available](https://www.cloudbees.com/jenkins/juc-2015/us-west)
- [Jenkins and Docker: Next Generation Continuous Delivery](https://www.linkedin.com/pulse/jenkins-docker-next-generation-continuous-delivery-khadija-kerissi)
- [Tutorial: Gestión de Configuración – Ansible + Vagrant + Jenkins](http://www.carlessanagustin.com/2015/08/20/tutorial-gestion-de-configuracion-ansible-vagrant-jenkins/)

### Red Hat Development
- [Red Hat Software Collections 2.1 now generally available](http://developerblog.redhat.com/2015/11/17/software-collections-2-1-generally-available/)
- [Red Hat developers blog, an Enterprise Developer’s Journey to the IoT](http://developerblog.redhat.com/2015/12/02/enterprise-developers-journey-to-iot/)

### SAP 
- [SAP cookbooks with chef](http://sapcc.github.io/sap-cookbook-docs/)

### DevOps
- [DevOps Library: The Best Videos for the Best Admins](http://devopslibrary.com/)
- [What to Expect From a DevOps Interview](https://dzone.com/articles/what-to-expect-from-a-devops-interview)
- [Why You’ll NEVER Nail That DevOps Interview](https://dzone.com/articles/why-youll-never-nail-that-devops-interview-1)
- [You will not become agile by implementing scrum](https://www.linkedin.com/pulse/you-become-agile-implementing-scrum-jurriaan-kamer)

### NoSQL
- [Introduction to NoSQL by Martin Fowler, video tutorial](https://www.youtube.com/watch?v=qI_g07C_Q5I)
- [NoSQL vs. SQL: Choosing a Data Management Solution](http://www.javacodegeeks.com/2015/10/nosql-vs-sql.html)

### Scalability
- [Scalable Internet Architectures" slides - Theo Schlossnagle how to build scalable production Internet services and... how not to build them](http://lethargy.org/~jesus/misc/Scalable%20Ti.pdf)

### Next Generation Firewalls
- [Dell SonicWALL TZ500 Firewall Review](http://www.storagereview.com/dell_sonicwall_tz500_firewall_review)
- http://livedemo.sonicwall.com
- [Disponible la 6ª generación de Dell SonicWALL TZ Series Firewalls con SonicOS 6.2. A tener en cuenta por Pymes interesadas en las nuevas conexiones de Internet para empresa (300 y 500Mbs)](http://www.dell.com/learn/us/en/uscorp1/press-releases/2015-04-28-dell-sonic-wall-tz-series)
- [SonicWALL Firewall vs. Fortinet Fortigate](http://www.firewalls.com/sonicwall_vs_fortigate)
- [Dell Security Adds 50 Percent Rebate On SonicWall TZ And NSA Appliances](http://www.crn.com/news/channel-programs/300077951/dell-security-adds-50-percent-rebate-on-sonicwall-tz-and-nsa-appliances.htm)

### Load Testing
- [JMeter Tutorial for Load Testing – The ULTIMATE Guide (PDF Download)](http://www.javacodegeeks.com/2014/11/jmeter-tutorial-load-testing.html)

### Metric monitoring
- [Linux cluster sysadmin — OS metric monitoring with colmux](http://www.rittmanmead.com/2014/12/linux-cluster-sysadmin-os-metric-monitoring-with-colmux/)
- [Netflix and linux performance analysis in 60 seconds](http://www.itworld.com/article/3010558/linux/netflix-linux-performance-analysis-in-60-seconds.html)

### Spark
- [Tools for Troubleshooting, Installation and Setup of Apache Spark Environments](https://dzone.com/articles/tools-for-troubleshooting-installation-and-setup-o)
- [Spark Streaming: What Is It and Who’s Using It?](http://www.datanami.com/2015/11/30/spark-streaming-what-is-it-and-whos-using-it/)

### Weblogic
- [WLST Scripting to Get WebLogic Libraries and Deployed Applications](https://blogs.oracle.com/practicalbpm/entry/wlst_scripting_to_get_weblogic)
- [Java Serialization Vulnerability Threatens Millions of Applications . Contrast security is promoting their solution for a vulnerability that affects WebLogic, WebSphere, JBoss, Jenkins, and OpenNMS.](https://dzone.com/articles/java-serialization-vulnerability-threatens-million)
- [Oracle WebLogic Server 12c Advanced Administration Cookbook](http://it-ebooks.info/book/3020/)

### Linux
- [Sysadmincasts.com: LVM Linear vs Striped Logical Volumes](https://sysadmincasts.com/episodes/27-lvm-linear-vs-striped-logical-volumes)
- [vim graphical cheat sheet](http://www.viemu.com/vi-vim-cheat-sheet.gif)
- [Linux: Keep An Eye On Your System With Glances Monitor](http://www.cyberciti.biz/faq/linux-install-glances-monitoring-tool/)
- [What are useful command-line network monitors on Linux](http://xmodulo.com/useful-command-line-network-monitors-linux.html)

### Wireshark and wiredit
- [WireEdit. First-Of-A-Kind and The Only Full Stack WYSIWYG Packet Editor Edit L2 - L7 with just a few clicks](https://wireedit.com/)
- [Wireshark 101: Transmission Control Protocol, video tutorial](https://www.youtube.com/watch?v=iX44XIZafiw)
- [Calculate HTTP response time in wireshark](http://www.thevisiblenetwork.com/2015/01/21/calculate-http-response-time-in-wireshark/)
- [HTTP Basic Authentication with wireshark](http://www.networkcomputing.com/applications/http-basic-authentication-primer/d/d-id/1323331)

### Startups
- [Startupxplore, mapa con todas las startups TI](https://startupxplore.com/)

### Python analytics
- [The State of Python for Data Science, PySS 2015](https://speakerdeck.com/chdoig/the-state-of-python-for-data-science-pyss-2015)
- [Distributed Computing on your Cluster with Anaconda (modern open source analytics platform powered by Python) - Webinar 2015](http://www.slideshare.net/continuumio/distributed-computing-on-your-cluster-with-anaconda-webinar-2015)
- [Jeff Reback's pandas tutorial at PyDataNYC2015, notebooks included](https://github.com/jreback/pydatanyc2015)
- [Python: The Next Big Thing in Big Data](https://dzone.com/articles/python-the-next-big-thing-in-big-data)
- [Talk Python to Me Podcast. Episode #34: Continuum: Scientific Python and The Business of Open Source](http://talkpython.fm/episodes/show/34/continuum-scientific-python-and-the-business-of-open-source)
- [Apache Zeppelin. Very cool for data exploration and data science](https://zeppelin.incubator.apache.org/)
- [Continuum Analytics PyData NYC videos are live! Check them out to see talks on Anaconda, Bokeh, pandas, and more, including the keynote from Continuum co-founders Peter Wang and Travis Oliphant](https://www.youtube.com/playlist?list=PLGVZCDnMOq0ourWlul1F7aYE30VQPaMRL)
- [Jessica Forde: Visualizing Wireless Router Timeseries Data with the Density API, Seaborn, and Pandas](https://www.youtube.com/watch?v=V85G5Q-Lj9o&feature=youtu.be&list=PLGVZCDnMOq0ourWlul1F7aYE30VQPaMRL)
- [Network data, also known as linked data, is the new frontier of data analysis](https://www.youtube.com/watch?v=wcrwASR5DCQ&index=42&list=PLGVZCDnMOq0ourWlul1F7aYE30VQPaMRL)

### AWS
- [Sysadmincasts.com: Introduction to Amazon Web Services (AWS)](https://sysadmincasts.com/episodes/29-introduction-to-amazon-web-services-aws)

### E-Learning
- [Red Hat Certified System Administrator - Exam EX200 - RHCSA (11€ con cupón de descuento)](https://www.udemy.com/red-hat-certified-system-administrator-exam-ex200-rhcsa/)
- [Learn To Run Linux Servers From Scratch (LPI Level 1-101)](https://www.udemy.com/draft/19966/)
- [Learn To Run Linux Servers Part 2 (LPI Level 1-102)](https://www.udemy.com/linuxacademy2/)
- [A Cloud Guru, AWS Certification Courses](https://acloud.guru)
- [Learning Puppet - Udemy](https://www.udemy.com/learning-puppet/)
- [Taming Big Data with Apache Spark - Hands On! - Udemy (~11-12€ with corresponding coupon)](https://www.udemy.com/taming-big-data-with-apache-spark-hands-on/?couponCode=SPARK15)
- [Basics of Scrum, Agile and Project Delivery](https://www.udemy.com/scrum-methodology/)
