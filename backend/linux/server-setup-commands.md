## Connect to server
```
ssh foo@[ip address]
```

## Add User
```
adduser foo
adduser foo sudo
```

## Update software
```
apt-get update && apt-get upgrade
```

## Setup Timezone
```
dpkg-reconfigure tzdata
```

## Install Emacs
```
apt  install e3
```

## Install Java
```
sudo apt install openjdk-8-jre-headless
```

## Security
Generate & copy SSH key to server:
```
// on remote machine
mkdir ~/.ssh
sudo chmod -R 700 ~/.ssh/

// on local machine
cd ~/.ssh
// create private/public keys
ssh-keygen
// complete steps, assume named foo & foo.pub

// copy public file to remote server
ssh-copy-id -i foo.pub [user]@[ip_address]

// register identity against newly created public key
eval "$(ssh-agent -s)" && ssh-add ~/.ssh/foo

// test by ssh'ing without needing to enter password
ssh [user]@[ip_address]
```

Edit security file:
```
cd /
cd etc/ssh
sudo emacs sshd_config
```
Change the following:
```
AddressFamily inet // questionable, messed up login
PermitRootLogin no
PasswordAuthentication no
ChallengeResponseAuthentication no
UsePAM yes
```
Restart security config changes: 
```
sudo systemctl restart sshd
sudo service ssh restart
reboot
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
## Firewall config
Check is activated:
```
sudo ufw status
```
if active, open up ports 80 & 443
```
sudo ufw allow in "WWW Full"
```
Reload
```
sudo ufw reload
```
Confirm by checking status once more.
