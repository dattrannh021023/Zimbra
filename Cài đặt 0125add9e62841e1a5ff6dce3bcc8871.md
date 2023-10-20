# Cài đặt

check `selinux` and `postfix` because usually, on CentOS 7, it will enable, so it needs to be disabled.

- **Disable `selinux`**

AZDIGI Tutorial

```
vi /etc/selinux/config

```

![https://azdigi.com/blog/wp-content/uploads/2022/04/CleanShot-2022-04-10-at-22.57.40.png](https://azdigi.com/blog/wp-content/uploads/2022/04/CleanShot-2022-04-10-at-22.57.40.png)

AZDIGI Tutorial

```
sestatus
SELinux status: disabled

```

- **Disable `postfix`**

`Postfix` is an `open-source mail transfer agent (MTA)` software for routing and sending mail. Released by IBM to replace the popular mail sender is `sendmail`. It is equipped with an operating system, so you can remove it to use Zimbra’s own service.

AZDIGI Tutorial

```
systemctl stop postfix
yum remove postfix -y

```

![https://azdigi.com/blog/wp-content/uploads/2022/04/CleanShot-2022-04-10-at-23.13.33.png](https://azdigi.com/blog/wp-content/uploads/2022/04/CleanShot-2022-04-10-at-23.13.33.png)

Next, update the system and reboot your VPS/server.

AZDIGI Tutorial

```
yum update -y ; reboot

```

While waiting for the system to update and reboot, you can take the next step.

# **Step 3: Update the mail record**

To install Zimbra, you need to point to 2 mail records as shown below:

TypeNameValueTTLAwebmailip-serverAutoMX@ or domainwebmail.domainAuto

![https://azdigi.com/blog/wp-content/uploads/2022/04/CleanShot-2022-04-10-at-23.54.05@2x-1024x397.png](https://azdigi.com/blog/wp-content/uploads/2022/04/CleanShot-2022-04-10-at-23.54.05@2x-1024x397.png)

# **Step 4: Set up the hostname**

You SSH back into the VPS or server (as in step 1). Then check if the current hostname of the VPS or server is correct and matches the record you pointed at in step 3, if not, you need to re-set the hostname.

AZDIGI Tutorial

```
hostnamectl set-hostname webmail.dattrantien.online
exec bash
```

After setting the hostname, go to the `hosts` file and add the following line: (remember to change the IP with your VPS or server IP)

AZDIGI Tutorial

```
vi /etc/hosts

```

AZDIGI Tutorial

```
127.0.0.1   localhost localhost.localdomain localhost4 localhost4.localdomain4
::1         localhost localhost.localdomain localhost6 localhost6.localdomain6
45.252.249.207 webmail.azdigi.online

```

# **Step 5: Install some necessary applications for Zimbra**

You execute the following command to install the necessary applications for Zimbra installation:

AZDIGI Tutorial

```
yum install unzip net-tools sysstat openssh-clients perl-core libaio nmap-ncat libstdc++.so.6 wget -y
```

# **Step 6: Install Zimbra Mail**

After you have installed the necessary applications, you create a Zimbra folder to download and install Zimbra.

AZDIGI Tutorial

```
mkdir zimbra && cd zimbra

```

Next, use the command below to download Zimbra. You can access the **[homepage](https://www.zimbra.com/downloads/zimbra-collaboration-open-source/)** to download the Zimbra source directly.

AZDIGI Tutorial

```
wget https://files.zimbra.com/downloads/8.8.15_GA/zcs-8.8.15_GA_3869.RHEL7_64.20190918004220.tgz --no-check-certificate

```

After the download is complete, extract the `.tgz` file and access the extracted folder to install Zimbra with the commands below:

AZDIGI Tutorial

```
tar zxpvf zcs*.tgz
cd zcs* && ./install.sh

```

AZDIGI Tutorial

```
[root@webmail zimbra]# cd zcs* && ./install.sh

Operations logged to /tmp/install.log.bnyHvXPW
Checking for existing installation...
    zimbra-drive...NOT FOUND
    zimbra-imapd...NOT FOUND
    zimbra-modern-ui...NOT FOUND
    zimbra-modern-zimlets...NOT FOUND
    zimbra-patch...NOT FOUND
    zimbra-mta-patch...NOT FOUND
    zimbra-proxy-patch...NOT FOUND
    zimbra-license-tools...NOT FOUND
    zimbra-license-extension...NOT FOUND
    zimbra-network-store...NOT FOUND
    zimbra-network-modules-ng...NOT FOUND
    zimbra-chat...NOT FOUND
    zimbra-connect...NOT FOUND
    zimbra-talk...NOT FOUND
    zimbra-ldap...NOT FOUND
    zimbra-logger...NOT FOUND
    zimbra-mta...NOT FOUND
    zimbra-dnscache...NOT FOUND
    zimbra-snmp...NOT FOUND
    zimbra-store...NOT FOUND
    zimbra-apache...NOT FOUND
    zimbra-spell...NOT FOUND
    zimbra-convertd...NOT FOUND
    zimbra-memcached...NOT FOUND
    zimbra-proxy...NOT FOUND
    zimbra-archiving...NOT FOUND
    zimbra-core...NOT FOUND

```

```
...
   zimbra-core...NOT FOUND
...
Do you agree with the terms of the software license agreement? [N]y
Use Zimbra's package repository [Y]y
Found zimbra-core (local)
Found zimbra-ldap (local)
Found zimbra-logger (local)
Found zimbra-mta (local)
Found zimbra-dnscache (local)
Found zimbra-snmp (local)
Found zimbra-store (local)
Found zimbra-apache (local)
Found zimbra-spell (local)
Found zimbra-memcached (repo)
Found zimbra-proxy (local)
Found zimbra-drive (repo)
Found zimbra-imapd (local)
Found zimbra-patch (repo)
Found zimbra-mta-patch (repo)
Found zimbra-proxy-patch (repo)

Select the packages to install
Install zimbra-ldap [Y]y
Install zimbra-logger [Y]y
Install zimbra-mta [Y]y
Install zimbra-dnscache [Y]y
Install zimbra-snmp [Y]y
Install zimbra-store [Y]y
Install zimbra-apache [Y]y
Install zimbra-spell [Y]y
Install zimbra-memcached [Y]y
Install zimbra-proxy [Y]y
Install zimbra-drive [Y]y
Install zimbra-imapd (BETA - for evaluation only) [N]y
Install zimbra-chat [Y]y
Checking required space for zimbra-core
Checking space for zimbra-store
Checking required packages for zimbra-store
zimbra-store package check complete.
Installing:
...
    zimbra-core
    ...
    zimbra-chat
...
The system will be modified.  Continue? [N]y
Beginning Installation - see /tmp/install.log.PtZTEKqZ for details...
                          zimbra-core-components will be downloaded and installed.
                            zimbra-timezone-data will be installed.
                          zimbra-common-core-jar will be installed.
                         zimbra-common-mbox-conf will be installed.
                   zimbra-common-mbox-conf-attrs will be installed.
                    zimbra-common-mbox-conf-msgs will be installed.
                  zimbra-common-mbox-conf-rights will be installed.
                           zimbra-common-mbox-db will be installed.
                         zimbra-common-mbox-docs will be installed.
                   zimbra-common-mbox-native-lib will be installed.
                         zimbra-common-core-libs will be installed.
                                     zimbra-core will be installed.
                          zimbra-ldap-components will be downloaded and installed.
                                     zimbra-ldap will be installed.
                                   zimbra-logger will be installed.
                           zimbra-mta-components will be downloaded and installed.
                                      zimbra-mta will be installed.
                      zimbra-dnscache-components will be downloaded and installed.
                                 zimbra-dnscache will be installed.
                          zimbra-snmp-components will be downloaded and installed.
                                     zimbra-snmp will be installed.
                         zimbra-store-components will be downloaded and installed.
                       zimbra-jetty-distribution will be downloaded and installed.
                                zimbra-mbox-conf will be installed.
                                 zimbra-mbox-war will be installed.
                             zimbra-mbox-service will be installed.
                       zimbra-mbox-webclient-war will be installed.
                   zimbra-mbox-admin-console-war will be installed.
                          zimbra-mbox-store-libs will be installed.
                                    zimbra-store will be installed.
                        zimbra-apache-components will be downloaded and installed.
                                   zimbra-apache will be installed.
                         zimbra-spell-components will be downloaded and installed.
                                    zimbra-spell will be installed.
                                zimbra-memcached will be downloaded and installed.
                         zimbra-proxy-components will be downloaded and installed.
                                    zimbra-proxy will be installed.
                                    zimbra-drive will be downloaded and installed (later).
                                    zimbra-imapd will be installed.
                                    zimbra-patch will be downloaded and installed (later).
                                zimbra-mta-patch will be downloaded and installed (later).
                              zimbra-proxy-patch will be downloaded and installed (later).
                                     zimbra-chat will be downloaded and installed (later).
Downloading packages (11):
...
   zimbra-core-components
   ...
   zimbra-proxy-components
      ...done
...
Removing /opt/zimbra
Removing zimbra crontab entry...done.
Cleaning up zimbra init scripts...done.
Cleaning up /etc/security/limits.conf...done.
Finished removing Zimbra Collaboration Server.
Installing repo packages (11):
...
   zimbra-core-components
   ...
   zimbra-proxy-components
      ...done
...
Installing local packages (27):
...
   zimbra-timezone-data
   ...
   zimbra-imapd
      ...done
...
Installing extra packages (5):
...
   zimbra-drive
   ...
   zimbra-chat
      ...done
...
Running Post Installation Configuration:
Operations logged to /tmp/zmsetup.20220411-024200.log
Installing LDAP configuration database...done.
Setting defaults...
DNS ERROR resolving MX for webmail.azdigi.online
It is suggested that the domain name have an MX record configured in DNS
Change domain name? [Yes]yes
Create domain: [webmail.azdigi.online]azdigi.online#Thay vào domain của bạn
	MX: webmail.azdigi.online (45.252.249.207)
	Interface: 127.0.0.1
	Interface: ::1
	Interface: 45.252.249.207
done.
Checking for port conflicts
Main menu
   1) Common Configuration:
   2) zimbra-ldap:                             Enabled
   3) zimbra-logger:                           Enabled
   4) zimbra-mta:                              Enabled
   5) zimbra-dnscache:                         Enabled
   6) zimbra-snmp:                             Enabled
   7) zimbra-store:                            Enabled
        +Create Admin User:                    yes
        +Admin user to create:                 admin@azdigi.online
******* +Admin PasswordUNSET#chưa set Password
        +Anti-virus quarantine user:           virus-quarantine.oz1ioypute@azdigi.online
        +Enable automated spam training:       yes
        +Spam training user:                   spam.wnlas9fe1o@azdigi.online
        +Non-spam(Ham) training user:          ham.97krutc9vl@azdigi.online
        +SMTP host:                            webmail.azdigi.online
        +Web server HTTP port:                 8080
        +Web server HTTPS port:                8443
        +Web server mode:                      https
        +IMAP server port:                     7143
        +IMAP server SSL port:                 7993
        +POP server port:                      7110
        +POP server SSL port:                  7995
        +Use spell check server:               yes
        +Spell server URL:                     http://webmail.azdigi.online:7780/aspell.php
        +Enable version update checks:         TRUE
        +Enable version update notifications:  TRUE
        +Version update notification email:    admin@azdigi.online
        +Version update source email:          admin@azdigi.online
        +Install mailstore (service webapp):   yes
        +Install UI (zimbra,zimbraAdmin webapps): yes
   8) zimbra-spell:                            Enabled
   9) zimbra-proxy:                            Enabled
  10) zimbra-imapd:                            Enabled
  11) Default Class of Service Configuration:
   s) Save config to file
   x) Expand menu
   q) Quit
Address unconfigured (**) items  (? - help)7
Store configuration
   1) Status:                                  Enabled
   2) Create Admin User:                       yes
   3) Admin user to create:                    admin@azdigi.online
** 4) Admin Password                           UNSET
   5) Anti-virus quarantine user:              virus-quarantine.oz1ioypute@azdigi.online
   6) Enable automated spam training:          yes
   7) Spam training user:                      spam.wnlas9fe1o@azdigi.online
   8) Non-spam(Ham) training user:             ham.97krutc9vl@azdigi.online
   9) SMTP host:                               webmail.azdigi.online
  10) Web server HTTP port:                    8080
  11) Web server HTTPS port:                   8443
  12) Web server mode:                         https
  13) IMAP server port:                        7143
  14) IMAP server SSL port:                    7993
  15) POP server port:                         7110
  16) POP server SSL port:                     7995
  17) Use spell check server:                  yes
  18) Spell server URL:                        http://webmail.azdigi.online:7780/aspell.php
  19) Enable version update checks:            TRUE
  20) Enable version update notifications:     TRUE
  21) Version update notification email:       admin@azdigi.online
  22) Version update source email:             admin@azdigi.online
  23) Install mailstore (service webapp):      yes
  24) Install UI (zimbra,zimbraAdmin webapps): yes
Select, or 'r' for previous menu [r]4
Password for admin@azdigi.online (min 6 characters): [JqA8eqasM]JqA8eqasM
Store configuration
   1) Status:                                  Enabled
   2) Create Admin User:                       yes
   3) Admin user to create:                    admin@azdigi.online
   4) Admin Password                           set#Đã set Password
   5) Anti-virus quarantine user:              virus-quarantine.oz1ioypute@azdigi.online
   6) Enable automated spam training:          yes
   7) Spam training user:                      spam.wnlas9fe1o@azdigi.online
   8) Non-spam(Ham) training user:             ham.97krutc9vl@azdigi.online
   9) SMTP host:                               webmail.azdigi.online
  10) Web server HTTP port:                    8080
  11) Web server HTTPS port:                   8443
  12) Web server mode:                         https
  13) IMAP server port:                        7143
  14) IMAP server SSL port:                    7993
  15) POP server port:                         7110
  16) POP server SSL port:                     7995
  17) Use spell check server:                  yes
  18) Spell server URL:                        http://webmail.azdigi.online:7780/aspell.php
  19) Enable version update checks:            TRUE
  20) Enable version update notifications:     TRUE
  21) Version update notification email:       admin@azdigi.online
  22) Version update source email:             admin@azdigi.online
  23) Install mailstore (service webapp):      yes
  24) Install UI (zimbra,zimbraAdmin webapps): yes
Select, or 'r' for previous menu [r]r
Main menu
   1) Common Configuration:
   2) zimbra-ldap:                             Enabled
   3) zimbra-logger:                           Enabled
   4) zimbra-mta:                              Enabled
   5) zimbra-dnscache:                         Enabled
   6) zimbra-snmp:                             Enabled
   7) zimbra-store:                            Enabled
   8) zimbra-spell:                            Enabled
   9) zimbra-proxy:                            Enabled
  10) zimbra-imapd:                            Enabled
  11) Default Class of Service Configuration:
   s) Save config to file
   x) Expand menu
   q) Quit
*** CONFIGURATION COMPLETE - press 'a' to apply
Select from menu, or press 'a' to apply config (? - help)a
Save configuration data to a file? [Yes]yes
Save config in file: [/opt/zimbra/config.15635] /opt/zimbra/config.15635
Saving config in /opt/zimbra/config.15635...done.
The system will be modified - continue? [No]yes
...
   Operations logged to /tmp/zmsetup.20220411-024200.log
   ...
   Finished installing common zimlets.
Restarting mailboxd...done.
...
Creating galsync account for default domain...done.
You have the option of notifying Zimbra of your installation.
This helps us to track the uptake of the Zimbra Collaboration Server.
The only information that will be transmitted is:
	The VERSION of zcs installed (8.8.15_GA_3869_RHEL7_64)
	The ADMIN EMAIL ADDRESS created (admin@azdigi.online)
Notify Zimbra of your installation? [Yes]yes/no
Notifying Zimbra of installation via http://www.zimbra.com/cgi-bin/notify.cgi?VER=8.8.15_GA_3869_RHEL7_64&MAIL=admin@azdigi.online
ERROR: Notification failed#Nếu chọn yes, mà mail admin@domain chưa tồn tại thì sẽ báo failed, có thể bỏ qua
Checking if the NG started running...done.
Setting up zimbra crontab...done.
Moving /tmp/zmsetup.20220411-024200.log to /opt/zimbra/log

Configuration complete - press return to exit
```

After the installation is complete, restart the Zimbra service with the following command:

AZDIGI Tutorial

```
su zimbra
cd && zmcontrol restart

```

AZDIGI Tutorial

```
[zimbra@webmail root]$ cd && zmcontrol restart
Host webmail.azdigi.online
	Stopping zmconfigd...Done.
	Stopping imapd...Done.
	Stopping zimlet webapp...Done.
	Stopping zimbraAdmin webapp...Done.
	Stopping zimbra webapp...Done.
	Stopping service webapp...Done.
	Stopping stats...Done.
	Stopping mta...Done.
	Stopping spell...Done.
	Stopping snmp...Done.
	Stopping cbpolicyd...Done.
	Stopping archiving...Done.
	Stopping opendkim...Done.
	Stopping amavis...Done.
	Stopping antivirus...Done.
	Stopping antispam...Done.
	Stopping proxy...Done.
	Stopping memcached...Done.
	Stopping mailbox...Done.
	Stopping logger...Done.
	Stopping dnscache...Done.
	Stopping ldap...Done.
Host webmail.azdigi.online
	Starting ldap...Done.
	Starting zmconfigd...Done.
	Starting dnscache...Done.
	Starting logger...Done.
	Starting mailbox...Done.
	Starting memcached...Done.
	Starting proxy...Done.
	Starting amavis...Done.
	Starting antispam...Done.
	Starting antivirus...Done.
	Starting opendkim...Done.
	Starting snmp...Done.
	Starting spell...Done.
	Starting mta...Done.
	Starting stats...Done.
	Starting service webapp...Done.
	Starting zimbra webapp...Done.
	Starting zimbraAdmin webapp...Done.
	Starting zimlet webapp...Done.
	Starting imapd...Done.

```

# **Step 7: Check Firewall and Open Port**

So you have completed the installation of zimbra and you need to check if the VPS/server is using Firewall or not. If yes, you need to open the following ports to work.

- **Ports you need to open**

```
25,80,110,143,443,465,587,993,995,5222,5223,9071,7071
```

Để cho phép các port này được bên ngoài truy cập cả TCP và UDP trên một hệ thống Linux, bạn có thể sử dụng iptables hoặc firewalld. Dưới đây, tôi sẽ cung cấp cách cấu hình bằng cả hai cách.

**Sử dụng iptables:**

1. Mở terminal và chạy lệnh sau với quyền root hoặc sudo để cấu hình iptables:

```bash
bashCopy code
sudo iptables -A INPUT -p tcp --match multiport --sports 25,80,110,143,443,465,587,993,995,5222,5223,9071,7071 -j ACCEPT
sudo iptables -A INPUT -p udp --match multiport --sports 25,80,110,143,443,465,587,993,995,5222,5223,9071,7071 -j ACCEPT

```

1. Lưu cấu hình iptables để nó tự động được áp dụng sau khi khởi động lại hệ thống:

```bash
bashCopy code
sudo service iptables save

```

**Sử dụng firewalld:**

1. Mở terminal và chạy các lệnh sau để cấu hình firewalld:

```bash
bashCopy code
sudo firewall-cmd --permanent --add-port=25/tcp
sudo firewall-cmd --permanent --add-port=80/tcp
sudo firewall-cmd --permanent --add-port=110/tcp
sudo firewall-cmd --permanent --add-port=143/tcp
sudo firewall-cmd --permanent --add-port=443/tcp
sudo firewall-cmd --permanent --add-port=465/tcp
sudo firewall-cmd --permanent --add-port=587/tcp
sudo firewall-cmd --permanent --add-port=993/tcp
sudo firewall-cmd --permanent --add-port=995/tcp
sudo firewall-cmd --permanent --add-port=5222/tcp
sudo firewall-cmd --permanent --add-port=5223/tcp
sudo firewall-cmd --permanent --add-port=9071/tcp
sudo firewall-cmd --permanent --add-port=7071/tcp

sudo firewall-cmd --permanent --add-port=25/udp
sudo firewall-cmd --permanent --add-port=80/udp
sudo firewall-cmd --permanent --add-port=110/udp
sudo firewall-cmd --permanent --add-port=143/udp
sudo firewall-cmd --permanent --add-port=443/udp
sudo firewall-cmd --permanent --add-port=465/udp
sudo firewall-cmd --permanent --add-port=587/udp
sudo firewall-cmd --permanent --add-port=993/udp
sudo firewall-cmd --permanent --add-port=995/udp
sudo firewall-cmd --permanent --add-port=5222/udp
sudo firewall-cmd --permanent --add-port=5223/udp
sudo firewall-cmd --permanent --add-port=9071/udp
sudo firewall-cmd --permanent --add-port=7071/udp

```

1. Sau khi cấu hình xong, bạn cần làm cho cấu hình này có hiệu lực bằng cách tải lại firewalld:

```bash
bashCopy code
sudo firewall-cmd --reload

```

Nhớ rằng cấu hình firewall như trên sẽ mở các port này cho truy cập từ bên ngoài, do đó, bạn cần đảm bảo rằng hệ thống của bạn có các biện pháp bảo mật khác để đảm bảo an toàn.

After checking, you can access zimbra admin by `IP:port` via `https` protocol!

- For example, https://45.252.249.207:7071/

Zimbra mail login interface

![https://azdigi.com/blog/wp-content/uploads/2022/04/CleanShot-2022-04-11-at-04.24.32.png](https://azdigi.com/blog/wp-content/uploads/2022/04/CleanShot-2022-04-11-at-04.24.32.png)

Login information includes:

- Username: admin@domain
- Password: Password is set in menu item 4

# **Note:**

After you log in, if you see `Trạng thái máy chủ` of the services not working, please reboot the VPS or server.

All services are not working.

![https://azdigi.com/blog/wp-content/uploads/2022/04/CleanShot-2022-04-11-at-04.34.13-1024x412.png](https://azdigi.com/blog/wp-content/uploads/2022/04/CleanShot-2022-04-11-at-04.34.13-1024x412.png)

And here are the results of my installation steps.

After rebooting VPS/server.

![https://azdigi.com/blog/wp-content/uploads/2022/04/CleanShot-2022-04-11-at-04.51.27-1024x486.png](https://azdigi.com/blog/wp-content/uploads/2022/04/CleanShot-2022-04-11-at-04.51.27-1024x486.png)