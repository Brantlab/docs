# Systems in Docker (Hipster VM's)

These are the systems I have in docker currently. 

As of 3/19/21
```
CONTAINER ID        IMAGE                             COMMAND                  CREATED             STATUS                PORTS                                            NAMES
cd82e35b7354        squidfunk/mkdocs-material         "mkdocs serve --dev-…"   10 minutes ago      Up 10 minutes         0.0.0.0:8001->8000/tcp                           pensive_wilson
17e971404544        cwmr/google-domains-ddns          "./google-domains-dd…"   46 hours ago        Up 46 hours                                                            elegant_jackson
7851b046ffb1        ghcr.io/linuxserver/code-server   "/init"                  47 hours ago        Up 9 seconds          0.0.0.0:8443->8443/tcp                           code-server
b30dc504e927        jc21/nginx-proxy-manager:latest   "/init"                  2 days ago          Up 2 days (healthy)   0.0.0.0:80-81->80-81/tcp, 0.0.0.0:443->443/tcp   nginx_app_1
a003badb8f4b        jc21/mariadb-aria:latest          "/scripts/run.sh"        2 days ago          Up 2 days             3306/tcp                                         nginx_db_1
6656bd7cb9bf        b4bz/homer:latest                 "/bin/sh /entrypoint…"   2 days ago          Up 37 hours           0.0.0.0:8080->8080/tcp                           confident_aryabhata
790e9b22d6e7        portainer/portainer               "/portainer"             11 months ago       Up 2 days             0.0.0.0:8000->8000/tcp, 0.0.0.0:9000->9000/tcp   portainer
dcb03666a82c        phpipam/phpipam-www:latest        "/sbin/tini -- /bin/…"   11 months ago       Up 2 days             0.0.0.0:8081->80/tcp                             phpipam_phpipam-web_1
2a7c79172329        phpipam/phpipam-cron:latest       "/sbin/tini -- /bin/…"   11 months ago       Up 2 days             80/tcp                                           phpipam_phpipam-cron_1
61fdc7e3bed9        mariadb:latest                    "docker-entrypoint.s…"   11 months ago       Up 2 days             3306/tcp                                         phpipam_phpipam-mariadb_1
```