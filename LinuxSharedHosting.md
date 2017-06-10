# linuxServerBaseConfiguration
Base configurations for linux servers

# Setup environment

## Install Nano if it is not installed

## Configure SSH
### Change Port / Disable Root login / ...etc.
```Shell
pico /etc/ssh/sshd_config  
#port 22  
/etc/init.d/sshd reload
```

## Configure Timezones

## Symlink Pico
```Shell
ln -sv /usr/bin/nano /usr/bin/pico
```

## Configure Hostname
```Shell
pico /etc/hosts
pico /etc/sysconfig/network
```
set
HOSTNAME=myserver.domain.com
```Shell
hostname hostname.domain.com
hostname #to check
/etc/init.d/network restart
```

## Reboot
```Shell
reboot
```

# Install cPanel if required
```Shell
cd /home && curl -o latest -L https://securedownloads.cpanel.net/latest && sh latest
# Update License 
/usr/local/cpanel/cpkeyclt
```
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



## Secure Temp
```Shell
pico /etc/fstab
```
set
no exec on temp
or run
```Shell
/scripts/securetmp
```


## Configure MySQL
/etc/my.cnf  
install openVPN


# Install CSF
```Shell
cd /usr/src
rm -fv csf.tgz
wget https://download.configserver.com/csf.tgz
tar -xzf csf.tgz
cd csf
sh install.sh
sh /usr/local/csf/bin/remove_apf_bfd.sh
```
* Configure it as needed
* Enable Passive mode for pureFTPd and open required ports


## Configure Backup as per Policy
* Incremential daily, retain 2
* Weekly, retain 2
* monthly, retain 3
* Off-site monthly, retain 2


## Don't Forget ioncube_encoder5_7.0.tar.gz


# Update everything and restart