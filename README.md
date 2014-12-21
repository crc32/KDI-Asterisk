KDI-Asterisk
============

## Setup Centos 6.6

Download minimal iso from Centos, & burn to CD or USB.

1. Install or upgrade existing system
2. Test media [skip]
3. Begin setup [Next]
4. Choose language [English]
5. Keyboard [U.S. English]
6. Type Devices [Basic Storage Devices]
7. Discard Existing Data [yes]
8. Hostname [localhost.localdomain] ** BEFORE YOU CLICK NEXT, DO STEP 8a. **
  8a. Configure Network [Click eth0 & Edit. Check:Connect Automatically then Apply & Close]
9. Time Zone [New York] ** Uncheck: System Clock Uses UTC **
10. Root Password [** make it very secure **]
11. Type Installation: Create Custom Layout with Primary Partition checked for 11a and 11c
  11a. Create -> Standard Partition -> Mount Point: /boot Type: ext4 Size:200  Fixed
  11b. Create -> Standard Partition -> Mount Point: blank Type: swap Size:2048 Fixed
  11c. Create -> Standard Partition -> Mount Point: /     Type: ext4 Size:Fill to Max Size
12. NEXT
13. FORMAT
14. WRITE CHANGES
15. Checked: Install boot loader on /dev/sda  Boot loader CentOS List: /dev/sda3
16. Reboot when finished
17. Login to new server as root
18. run yum -y update
19. Run yum -y install nano
20. Edit /etc/sudoers with nano, and allow wheel group to use sudo
21. add new user, set password, add user to wheel
22. nano /etc/selinux/config  -> change enforcing to permissive (see here for why: http://www.pedro.kiefer.com.br/2014/04/selinux-freepbx)
23. reboot
24. login as new user
25. sudo su
26. yum groupinstall core
27. yum groupinstall base
28. yum install gcc gcc-c++ lynx bison mysql-devel mysql-server php php-mysql php-pear php-mbstring tftp-server httpd make ncurses-devel libtermcap-devel sendmail sendmail-cf caching-nameserver sox newt-devel libxml2-devel libtiff-devel audiofile-devel gtk2-devel subversion kernel-devel git subversion kernel-devel php-process crontabs cronie cronie-anacron wget vim php-xml uuid-devel libtool sqlite-devel net-tools curl perl perl-CPAN
29. Continue to follow the instructions here: http://wiki.freepbx.org/display/HTGS/Installing+FreePBX+12+on+CentOS+6.5
 

