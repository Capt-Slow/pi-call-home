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

Configuring a Socks proxy to allow for browser access.

Connect to the Pi using the following. This will create a Socks proxy through port 12345.
```
$ ssh -l pi -p 2222 -D 12345 localhost
```
Next is to execute a web browser on "your" server from your local. You can do that with the following:
```
$ ssh -X -f -T your@server_ip firefox
```

From here you can change how firefox connect to the internet through it's advanced settings. Set proxy to:
```
127.0.0.1 12345
```
You now can browse the internet using the network the Pi is connected.
