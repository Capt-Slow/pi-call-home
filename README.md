# pi-call-home
Script to allow a raspberry pi to call home when plugged into a network 
Steps:
1) chmod 700 ~/create_ssh_tunnel.sh
2) crontab -e
3) */1 * * * * ~/create_ssh_tunnel.sh > tunnel.log 2>&1

To log into the pi from the server:
1) ssh -l pi -p 2222 localhost
