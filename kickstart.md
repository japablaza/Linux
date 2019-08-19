# Kickstart

- How Do You Perform a Kickstart Installation?  
  `https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/installation_guide/sect-kickstart-howto`

- Kickstart File  
  Post new installation, open `anaconda-ks.cfg`, located in the `/root/` directory.
  Copy this file, make any chages you need, and use the resulting file as Kickstart

- Kickstart Configuration Tool  
  `https://access.redhat.com/labs/kickstartconfig`

- Verifying the Kickstart File  
  Install *pykickstart* with `yum install pykickstart` and then validate with `ksvalidator /path/ks_file.ks`
