# Red Hat Enterprise Linux 6 remote deployment on Dell PowerEdge R720 & KVM virtualization with qcow2 pre-allocation (MHT document, year 2012)
- [The evernote online version of this MHT document](http://bit.ly/Ulb98Q )
Summary of MHT document: Best practices, recommendations and notes: Red Hat Enterprise Linux 6.3 remote installation/deployment on DELL PowerEdge R720 (12G), KVM hypervisor, Tomcat7, Uptime &amp; Performance Tips.

This MHT/MHTML document is not rendered by github. An MHT document is easier to share and read compared to the online version, and can be open by the following tools:
- Browsers: Microsoft Internet Explorer, Firefox (with the Mozilla Archive Format extension), Chrome (extension required), Opera
- Editors: Evernote, Microsoft Word 2010, Microsoft Powerpoint 2010, WizBrother WizHtmlEditor, Terra Informatics BlockNote.Net, Kingsoft Writer.

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



