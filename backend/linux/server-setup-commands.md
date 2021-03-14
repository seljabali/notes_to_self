## Update software
```
apt-get update && apt-get upgrade
```

## Setup Timezone
```
dpkg-reconfigure tzdata
```

## Security
Edit security file:
```
cd etc/ssh
sudo emacs sshd_config
```
Change the following:
```
# Authentication
PermitRootLogin no
# To disable tunneeled clear text passwords
PasswordAuthentication no
#Port 22
AddressFamily inet
```
Restart security config changes: 
```
sudo systemctl restart sshd
```

## Add User
```
sudo useradd -d /home/foo -m foo
passwd foo

su - foo //switch user

chown foo /home/foo

su - root
usermod -G sudo foo
```

## Setup Hosts
Hostname
```
emacs /etc/hostname
	www
```
Hosts
```
emacs /etc/hosts
	127.0.0.1 www.dhk.lol dhk.lol www localhost
	127.0.1.1 www
```
Check values
```
hostname
	www
hostname -d
	dhk.lol
hostname -f
	www.dhk.lol
```
