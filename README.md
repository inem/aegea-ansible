README.md

# Install Ansible

## On local machine (with macOS):

```
sudo easy_install pip
sudo pip install ansible
```

# Prerequisites

1. Boot up an instance of Ubuntu Wily(15.10)
2. Set up DNS record: "A blog.example.com 111.11.11.11"
3. Rename hosts example to hosts and put your domain name there
4. Modify vars section of playbook if needed
5. Before executing ansible script, run these lines manually to install LAMP stack:

```
apt-get install tasksel 
tasksel install lamp-server
```

Manual installation of LAMP stack is a mess. I found it much easier to get it working with tasksel: http://askubuntu.com/questions/359362/how-to-correctly-install-apache2-php5-mysql-and-phpmyadmin


# Run script:

`ansible-playbook -i hosts setup.yml -uroot`


#TODO:
- figure out what causes bug with uploads and fix th problem
- copy additional stuff into separate folder
- setup sendmail - http://blog.antoniokov.com/all/blogengine-on-digitalocean/ (ru)
- refactor playbook with ansible roles
- make sure that DNS record line is correct
- get rid of tasksel?
- SSL config?

# Misc

## Related LAMP stack installationlinks:

- https://www.digitalocean.com/community/tutorials/how-to-install-linux-apache-mysql-php-lamp-stack-on-ubuntu-16-04
- https://www.digitalocean.com/community/tutorials/how-to-configure-apache-using-ansible-on-ubuntu-14-04
- https://docs.google.com/document/d/14Sb3m9NvNDKMeVF7t9rlhop-S1d_chSNFGbJvnOVe9I/edit#
- http://blog.antoniokov.com/all/blogengine-on-digitalocean/ (ru)

## Non-working but useful recipes:
- https://github.com/fourkitchens/server-playbooks
- http://labs.qandidate.com/blog/2013/11/21/installing-a-lamp-server-with-ansible-playbooks-and-roles/

## Related ansible links:

- http://docs.ansible.com/ansible/unarchive_module.html
- http://docs.ansible.com/ansible/mysql_db_module.html
- http://docs.ansible.com/ansible/copy_module.html
- http://docs.ansible.com/ansible/file_module.html
