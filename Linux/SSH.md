# SSH (cheat sheet)

```
ssh-keygen
```

```
ssh-copy-id user@host
```

##  Correct permissions on .ssh

```
chmod 700 /home/user/.ssh
chmod 600 /home/user/.ssh/authorized_keys
```

##  ~/.ssh/config (in test env)

```
StrictHostKeyChecking no
UserKnownHostsFile /dev/null
LogLevel ERROR
```