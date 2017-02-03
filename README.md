# Docker-help
Problems faced during docker

While using docker in ubuntu VM. It may use  different dns from the one it should use.
So it will not detect the host "archive.ubunut.com" In that case follow the follwing

1. find your dns by using nmcli dev show | grep 'IP4.DNS'
2. check docker run --dns x.x.x.x busybox nslookup google.com command is running
3.If that works, That should be your dns for docker container
4. sudo gedit /etc/docker/daemon.json

and type

{
    "dns": ["x.x.x.x", "8.8.8.8"]
}

5.sudo service docker restart


win! win! win 
