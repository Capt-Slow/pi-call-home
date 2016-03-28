# pi-call-home
Script to allow a raspberry pi to call home when plugged into a network 
Steps:
```sh
$ chmod 700 ~/create_ssh_tunnel.sh
```
```sh
$ crontab -e
```
```sh
$ */1 * * * * ~/create_ssh_tunnel.sh > tunnel.log 2>&1
```
To log into the pi from the server:
```
$ ssh -l pi -p 2222 localhost
```
