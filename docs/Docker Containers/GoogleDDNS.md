# Google DDNS
## Why do I run this?
I run this to update a dynamic DNS record for my home. I used to do this with PFsense but I have since decomissioned that for a USG pro that was donated to my homelab. This was a quick easy way to get the dynamic record up and working again with little fuss.

## My install

The command I ran to stand up the container. It took less than 30 seconds and dynamic DNS was going.  
```
docker run -v /etc/localtime:/etc/localtime -e USERNAME=<USER> -e PASSWORD=<PASS> -e HOSTNAME=<DDNS DOMAIN> -e INTERVAL=5m cwmr/google-domains-ddns
```

Steps for the commands

1. Create a google domains dynamic DNS record
    ![](https://i.imgur.com/VBxsjBq.png)

2. Grab the Username and Password
    ![](https://i.imgur.com/6jvurfZ.png)

3. Open a connection to your docker host and fill in your `<DDNS Domain> <USER> <PASS>` Example Below
```
docker run -v /etc/localtime:/etc/localtime -e USERNAME=userthatexists -e PASSWORD=passthatdoesexist -e HOSTNAME=docs.brantlab.com -e INTERVAL=5m cwmr/google-domains-ddns
```

## Source
I used this project [Here](https://github.com/chadweimer/docker-google-domains-ddns).