# letsHAP
Easy manage letsencrypt certificates in HAProxy environment

To enable auto renew, add a line in /etc/crontab (or via crontab -e as root) :

`` *       23      *       *       *       root    letsHAP --renew-all ``


 ```
 ~ Usage : letsHAP [Option] [PARAM]

 Beware : First start, you have to run letsHAP --register [EMAIL]

Options
-------

-re | --register [EMAIL]
* Create /etc/letsencrypt directory after creating your account on let's Encrypt

-a  |--add [DOMAIN]
* Add certs files for the domain
* Create renewal config file for that domain
* Add and refresh HAProxy's ssl cert list
* HAProxy : Check config file && restart

-ra |--renew-all :
* Renew what's needed for renewed domains
* Regenerate .pem files for HAProxy
* HAProxy : Check config file && restart

-rev|--revoke [DOMAIN]
* to be coded if needed

```
