# Setting-up a new host

All on the Expert Stats worker.
## Use a existing Tmux session or open a new one
```
tmux ls
```

```
tmux attach -t {session}
```
## Access to the workspace container

```
docker exec -it workspace bash
cd expert-stats
```
##  Check the access to the host

```
ssh phonesystem@host
```

If the connection is established normally, exit.
##  Launch the process 

```
php artisan pbx3cx:host-process granitsmichelmaffre.my3cx.fr
```
## Add the host to the process

Exit the docker workspace.

Add the host to the hosts lists.

```
echo hostname >> scripts/hosts
```
