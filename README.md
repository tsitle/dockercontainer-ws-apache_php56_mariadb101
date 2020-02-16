# Apache2 + PHP 5.6 + MariaDB 10.1 Client Docker Container for AARCH64, ARMv7l, X86 and X64

For hosting PHP powered websites.

## Required Docker Image
The Docker Image **ws-apache-php56-mariadb101-\<ARCH\>** will automaticly be downloaded from the Docker Hub.  
The source for the image can be found here [https://github.com/tsitle/dockerimage-ws-apache\_php56_mariadb101](https://github.com/tsitle/dockerimage-ws-apache_php56_mariadb101).

## Docker Container usage
- copy the file `docker-compose-<ARCH>-SAMPLE.yaml` to `docker-compose.yaml`
- edit the file as needed
- run `$ ./dc-ws-apache.sh up`

To stop the container run `$ ./dc-ws-apache.sh down`

## Docker Container configuration

- CF\_PROJ\_PRIMARY\_FQDN [string]: FQDN for website (e.g. "mywebsite.localhost")
- CF\_SET\_OWNER\_AND\_PERMS\_WEBROOT [bool]: Recursively chown and chmod CF\_WEBROOT?
- CF\_WWWDATA\_USER\_ID [int]: User-ID for www-data
- CF\_WWWDATA\_GROUP\_ID [int]: Group-ID for www-data
- CF\_WWWFPM\_USER\_ID [int]: User-ID for wwwphpfpm
- CF\_WWWFPM\_GROUP\_ID [int]: Group-ID for wwwphpfpm
- CF\_ENABLE\_CRON [bool]: Enable cron service?
- CF\_LANG [string]: Language to use (en\_EN.UTF-8 or de\_DE.UTF-8)
- CF\_TIMEZONE [string]: Timezone (e.g. 'Europe/Berlin')

## Using cron
If you'd like to use cron you'll also need to copy the file `mpcron/crontab-template` to
`mpcron/<USERNAME>`.  
E.g. for installing a crontab for the user "www-data" copy the file to `mpcron/www-data`.  
Then uncomment the mountpoint for that file in the `docker-compose.yaml`.
