# letsHAP
Easy manage letsencrypt certificates in HAProxy environment

To enable auto renew, add a line in /etc/crontab (or via crontab -e as root) :

`` *       23      *       *       *       root    letsHAP --renew-all ``


 ```
 ~ Usage : letsHAP [Option] [PARAM]

 Beware : First start, you have to run $0 --register [EMAIL]

Options
-------
-dry | --dry-run
* Simulation mode

-re | --register [EMAIL]
* Create your account on let's Encrypt and /etc/letsencrypt directory

-a  |--add [DOMAIN]
* Create and install certificate for one or multiple domains (SAN - max renewal : 200/week)
* Create renewal config file(s) for  domain(s)
* Add and refresh HAProxy's ssl cert list  
* Check config file && restart HAProxy

-ra |--renew-all :
* Renew what's needed for renewed domains
* Regenerate .pem files for HAProxy
* HAProxy : Check config file && restart

-rev|--revoke [DOMAIN]
* to be coded if needed


```
