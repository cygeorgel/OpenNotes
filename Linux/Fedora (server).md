# Fedora (server)

Things I do after installing a new Fedora server.


##  Install latest updates

```
dnf update
```

##  Install Vim as default editor

```
dnf install -y vim-default-editor --allowerasing
```

## Change SSH port

Edit a file /etc/ssh/sshd_config.d/custom.conf

```
Port **022
```

### Configure SELinux for the new port

```
dnf install policycoreutils-python-utils
```

```
semanage port -a -t ssh_port_t -p tcp **022
```

and check with:

```
semanage port -l | grep ssh
```

expected result:

```
ssh_port_t                     tcp      **022, 22
```

## Install and configure Firewalld

```
dnf install firewalld
systemctl enable --now firewalld
firewall-cmd --permanent --add-service=ssh
firewall-cmd --permanent --service="ssh" --add-port "**022/tcp"
firewall-cmd --reload
systemctl restart sshd
```

## Install and configure Fail2ban

```
dnf install fail2ban
systemctl enable --now fail2ban
```

Edit /etc/fail2ban/jail.local

```
[sshd]
enabled = true
port = **022
filter = sshd
logpath = /var/log/secure
maxretry = 3
bantime = 86400
findtime = 3600
```

Then restart Fail2ban

```
systemctl restart fail2ban
```

## Disable password authentication

Edit /etc/ssh/sshd_config.d/50-cloud-init.conf

```
PasswordAuthentication no
```

## Install Cron

```
dnf install cronie
systemctl start crond.service
systemctl enable crond.service
```

## Install mailx

To provide you with a handy way to send emails from bash scripts.

```
dnf install mailx
```

Configure mailx for users

```
vim .mailrc
```

Example of smtp configuration:

```
set smtp-use-starttls
set ssl-verify=ignore
set smtp=smtp://{smtp}:587
set smtp-auth=login
set smtp-auth-user={login}
set smtp-auth-password={password}
set from={from}
```

## Git

```
dnf -y install git-all
```

## Other stuff

Not mandatory, this is for comfort

### tmux

```
dnf install tmux
```

### htop

```
dnf install htop
```

### kitty

```
dnf install kitty
```

## Docker

```
dnf -y install dnf-plugins-core
dnf -y config-manager --add-repo https://download.docker.com/linux/fedora/docker-ce.repo
dnf -y install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
groupadd docker && usermod -aG docker fedora
systemctl enable docker
systemctl start docker
```


