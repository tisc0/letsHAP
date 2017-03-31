# letsHAP
Easy manage letsencrypt certificates in HAProxy environment

To enable auto renew, add a line in /etc/crontab (or via crontab -e as root) :

`` *       23      *       *       *       root    letsHAP --renew-all ``

``
 ~ Usage : $0 [Option] [PARAM]

 Beware : First start, you have to run $0 --register [EMAIL]

Options
-------

-re | --register [EMAIL]
* Create /etc/letsencrypt directory after creating your account on let's Encrypt

-a  |--add [DOMAIN]
* Add certs files for the domain
* Create renewal config file for that domain
* Add and refresh HAPROXY's ssl cert list
* HAPROXY : Check config file && restart

-ra |--renew-all : 
* renew what's needed for renewed domains

-rev|--revoke [DOMAIN]
* to be coded... any help welcome

``
