# letsHAP
Easy manage letsencrypt certificates in HAProxy environment

## Install
- Edit letsHAP script file and customize it (HAProxy instance name + conf file), and enable it.
- make install (will copy letsHAP in /usr/local/bin/letsHAP)

## Auto-renew
To enable auto renew, add a line in /etc/crontab (or via crontab -e as root) :

`` *       23      *       *       *       root    letsHAP --renew-all ``

## HAProxy preparation
We made it easy : you'll find the minimal to config your HAProxy in haproxy.cfg.

## Usage
You can get it with 'letHAP -h'


 ```
 ~ Usage : letsHAP [Option] [PARAM]

 Beware : First start, you have to run $0 --register [EMAIL]

Options
-------
-dry |--dry-run
* Simulation mode

-re |--register [EMAIL]
* Create your account on let's Encrypt and /etc/letsencrypt directory

-a |--add [DOMAIN]
* Create and install certificate for one or multiple domains (SAN - max renewal : 200/week)
* Create renewal config file(s) for  domain(s)
* Add and refresh HAProxy's ssl cert list  
* Check config file && restart HAProxy

-ra |--renew-all :
* Renew what's needed for renewed domains
* Regenerate .pem files for HAProxy
* HAProxy : Check config file && restart

-rev |--revoke [CERTNAME]
* Revoke in place a certificate (don't move any file) and all the SANs attached to it

-del |--delete
* Delete completely a cert chain
* Clean up and restart HAProxy

-h |--help
* Getting this how to use details

Error codes
-----------
exit 1 : Undefined error
exit 2 : Certname doesn't exists
exit 3 : Certificate already revoked
exit 4 : Undefined revocation error
exit 9 : Script's not enabled


```
