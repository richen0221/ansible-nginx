Nginx and PHP-FPM
=========

The playbook will install Nginx, php-fpm and vsftpd.

At the same time, it will create a `PRJ_USER_NAME` for developer upload project files via FTP.

The folder structure is as below: 

1. `PRJ_USER_NAME`'s home directory is located in `/home/project-name/`.
2. Nginx working dir is `/home/project-name/www/`.
3. Nginx log files is `/home/project-name/logs/`.

Requirements
------------

This script is for CentOS 7 only.

Please install the `provision.yml` playbook first.

Provide the `secondary_user` in the `nginx.yml`'s  `remote_user` for login.

Please place the `server-ip` at the `hosts` block in the `nginx.yml` file.

Role Variables
--------------

Change the variables settings in the `/roles/nginx/vars/main.yml`.

To specify the php's version, changing the `PHP_VERSION` variable.

The support versions and representations are as below:
   
`remi` (is php5.4), `remi-php55`, `remi-php56`, `remi-php70`, `remi-php71`

The `PRJ_USER_NAME`'s password (`PRJ_USER_PASSWORD`) hash must copy from the `/etc/shadow` password.

    PHP_VERSION: remi-php72
    PRJ_USER_NAME: web
    PRJ_USER_PASSWORD: 
    PRJ_NAME: web


Usage
----------------

After the provision, you can run the playbook directly as bleow :

`ansible-playbook nginx.yml`
``````

License
-------

BSD

Author Information
------------------

Ricky Chen
