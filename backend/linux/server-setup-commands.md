## Connect to server
```
ssh foo@[ip address]
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
scp foo.pub [user]@[ip_address]:~/.ssh/ 

// register identity against newly created public key
eval "$(ssh-agent -s)" && ssh-add ~/.ssh/foo

// test by ssh'ing without needing to enter password
ssh [user]@[ip_address]
```

Edit security file:
```
cd etc/ssh
sudo emacs sshd_config
```
Change the following:
```
AddressFamily inet
PermitRootLogin no
PasswordAuthentication no
ChallengeResponseAuthentication no
UsePAM yes
```
Restart security config changes: 
```
sudo systemctl restart sshd
or 
sudo service ssh restart
```

## Add User
```
adduser foo
adduser foo sudo
```
or
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
