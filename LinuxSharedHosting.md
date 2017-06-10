# linuxServerBaseConfiguration
Base configurations for linux servers

# Setup environment

## Install Nano if it is not installed

## Configure SSH
### Change Port / Disable Root login / ...etc.
```bash
pico /etc/ssh/sshd_config  
#port 22  
/etc/init.d/sshd reload
```

## Configure Timezones

## Symlink Pico
`ln -sv /usr/bin/nano /usr/bin/pico`

## Configure Hostname
`pico /etc/hosts
pico /etc/sysconfig/network
HOSTNAME=myserver.domain.com
hostname hostname.domain.com
hostname
/etc/init.d/network restart`

## Reboot
`reboot`

# Install cPanel if required
`cd /home && curl -o latest -L https://securedownloads.cpanel.net/latest && sh latest`
* Update License `/usr/local/cpanel/cpkeyclt`
## Go through settings and updates
## Setup Apache as required
## Name server (Bind)
## Configure nameservers domains
## Configure Address Records for Nameservers & Hostname
## FTP Server PureFTPd
## Enable cPHulk
## Install Common Set of Perl Modules
## Enable 
* DKIM
* SPF
* Thunderbird and Outlook autodiscover and autoconfig support
* Email delivery retry time (15 Minutes)
* Track email origin via X-Source email headers
* Notify admin or reseller when disk quota reaches “warn” state
## Disable Compilers
## Install ClamAV 
## Apache Symlink Protection
## 

pico /etc/fstab
no exec on temp
/scripts/securetmp




## Configure MySQL
/etc/my.cnf
install openVPN


# Install CSF
`cd /usr/src
rm -fv csf.tgz
wget https://download.configserver.com/csf.tgz
tar -xzf csf.tgz
cd csf
sh install.sh

sh /usr/local/csf/bin/remove_apf_bfd.sh
`
## Configure it as needed
## Enable Passive mode for pureFTPd and open required ports





## Configure Backp as per Policy
### Incremential daily, retain 2
### Weekly, retain 2
### monthly, retain 3
### Off-site monthly, retain 2












## Don't Forget ioncube_encoder5_7.0.tar.gz






# Update everything and restart