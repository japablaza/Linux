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
  `hostname -I` --> Display all network address of the host

## Secure Apache HTTPs with SSL

- Install SSL module
  `yum install mod_ssl openssl`

- Self-signed Certificate
  `openssl genrsa -out ca.key 2048` --> Generat private key `ca.key`
  `openssl req -new -key ca.key -out ca.csr` --> Generate cert signing request `ca.csr`
  `openssl x509 -req -days 365 -in ca.csr -signkey ca.key -out ca.crt` --> Generate a self-signed certificate `ca.crt` of X509 type valid for 365 key

  `cp ca.crt /etc/pki/tls/certs/`
  `cp ca.key /etc/pki/tls/private/`
  `cp ca.csr /etc/pki/tls/private/`

- Set Up The Certificates
  `vi /etc/httpd/conf.d/ssl.conf`
  	 Under `<VirtualHost _default_:443>
		`DocumentRoot "/var/www/html"` --> The website where you are going to use the SSL cert
		`ServerName {LocalHost IP}:443 --> You can use `hostname -I` to find the local IP address
		`SSLEngine on` --> Activate SSL
		`SSLCertificateFile /etc/pki/tls/certs/ca.crt`
		`SSLCertificatekeyFile /etc/pki/tls/private/ca.key`
  
  `systemctl restart httpd`
  
