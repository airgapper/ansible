
#Deploy

User installed with sudo privelege

I.E. usermod -aG sudo USERNAME 

sudo ansible-playbook -i my-inventory.hosts deploy_key.yml  --ask-become-pass -vvv


# USING NGINX, LETSENCRYPT

## REQUIRMENTS



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

## Create Password

CREATE PASSWORD:

```  mkpassed --method=SHA-512 ```

(It will ask for a password)

Add output to password portion of users.yml file


## Copy your public Key
 Copy the public key info to the  "key: " variable below



## Create users.yml file

There are other bits you can add like if you are creating sql.

Enter Following

```
---
    users:
      - name: Some user
        state: present
        passwd: "(PASSWORD FROM mkpassed)"
        key: "ssh-rsa AAAAB3NzaC1yc2EAAAADAAAAAAAAAAAAAAAH6iNG6JnP+g3A9GOrRurDN0V2g64W8nBXX49rbwlTMPfN7kaF2KdcfYDUj9ANub05ODSqwpkbT9YsAJLS3B01AWP/76MZeDxDbMcd8h
4FbMXU61tvPwj51ZujlK0PRbNxUGC6LdaYG1mcEj423523b/25235326tadsfae54341c/kPTY2sdqsQ8LBDL1jQdIsNasf9a87fav0987a0s9f5 someuser@
system"
        mysql_root_password: "sql passA"
    users_to_remove:
      - name: Unneeded_user

