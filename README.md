
#Deploy

User installed with sudo privelege

I.E. usermod -aG sudo USERNAME 

sudo ansible-playbook -i my-inventory.hosts deploy_key.yml  --ask-become-pass -vvv


# USING NGINX, LETSENCRYPT

## REQUIRMENTS



CREATE PASSWORD:

	 mkpassed --method=SHA-512

It will ask for a password


## PACKAGES
Whois package has this program if above fail 
 ``` apt install whois ```


WILL TAKE FOREVER TO RENDER dhpram 2048




## Create Ansible Vault File

``` ansible-vault create passwords.yml ```

Enter Following

```
username: ansible-user@internal
password: redhat
cloud_init_username: root
cloud_init_password: redhat
```


