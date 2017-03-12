# letsHAP
Easy manage letsencrypt certificates in HAProxy environment

Beta for 3 months (waiting renewal period to test automatic renew).
To enable auto renew, add a line in /etc/crontab (or via crontab -e as root) :

`` *       23      *       *       *       root    letsHAP --renew-all ``
