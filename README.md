ansible-php5fpm for Debian/Ubuntu
============

Ansible role for installing php-fpm on the your Debian/Ubuntu system.

## php5.6 by default

## OPcache disabled

Feel free to configure opcache to really speed up your php apps `/etc/php5/fpm/conf.d/05-opcache.ini`.

## Overwrite Default Variables

The `vars/main.yml` file should contain your list of packages you want to install in order to override defaults found in `defaults/main.yml`.

```yml
---
php_ppa: "ondrej/php5-5.6"
php_user: www-data
php_group: www-data
php_listen: /var/run/php5-fpm.sock
php_timezone: UTC

php_default_packages:
  - python-software-properties
  - php5-cli
  - php5-fpm
  - php5-mcrypt
  - php5-imagick
  - php5-curl
  - php5-gd
  - php5-mysql
  - php5-xmlrpc

php_app_name: "My Awesome App"
```

Additionally, you can overwrite the variables as part of your playbook.

```yml
---
...
  vars:
    php_ppa: "ondrej/php5-5.6"
    php_user: www-data
    php_group: www-data
    php_listen: /var/run/php5-fpm.sock
...
```
