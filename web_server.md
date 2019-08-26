# [Web Server]

*Link*: `https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/system_administrators_guide/ch-web_servers`

## General commands
- `apachectl graceful` it is used by default when the service is reloaded
- `apachectl configtest` is used by default when the service is stopped
- `HTTPd` uses private `/tmp` directory
-
## Basic Installation 

- Installing Apache
  `yum update -y`
  `yum install https -y`

- Check the Apache installation 
  `systemctl status httpd.service`
  `systemctl start  httpd.service`
  `systemctl enable httpd.service` --> The service starts after reboot
