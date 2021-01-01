
###USAGE:

```
ansible-playbook playbook.yml -HOSTS.yml --limit myhostname.com 

```

Your domain name will need to be resolvable in DNS
I.E
``myhostname.com = 192.168.0.1``



## HOSTS.yml file


```
---
websites:
  hosts:
    myhostname.com:
      ansible_user: sudo_user_used_in_deploy
      ansible_password: sudo_user_pass
      ansible_host: 192.168.0.1
      letsencrypt_email: info@myhostname.com
      domain_name: myhostname.com

    myotherdomain.com:
      ansible_user: sudo_user_used_in_deploy
      ansible_password: sudo_user_pass
      ansible_host: 192.168.0.2
      letsencrypt_email: info@myotherdomain.com
      domain_name: myotherdomain.com6

  vars:
    ansible_python_interpreter: /usr/bin/python3
    ansible_ssh_port: 22

...


```
