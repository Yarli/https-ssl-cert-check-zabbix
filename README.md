Script to check validity and expiration of TLS/SSL certificate for given host, port and (optional) servername for TLS SNI.
Adapted from selivan/https-ssl-cert-check-zabbix

May be used standalone or with Zabbix(user parameters example included).

**Installation on Zabbix server**
Copy ssl_cert_check.sh to /usr/lib/zabbix/externalscripts
```
cd /usr/lib/zabbix/externalscripts
chmod 755 ssl_cert_check.sh
chown zabbix:zabbix ssl_cert_check.sh
```
Import template_zabbix_ssl_checks.xml into Zabbiz templates via the Zabbix UI.
Assign the template to your hosts that you want to monitor
Ensure you have a valid entry in each hosts "DNS" field, otherwise it'll fail to run the SSL checks.
The default port 443 will be used to connect and check the SSL certificate. If you use a different port for a specific host, then do this:
#Ggo to the Macros tab on your host in Zabbix
#Click "Inherited and host macros"
#Press  the "Change" link next to that macro.
#Change the value for {$SSL_PORT} from 443 to your desired port
#Press Update button at the bottom of your Macros page.
