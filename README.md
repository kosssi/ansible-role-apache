# ansible-role-apache

[![Build Status](https://travis-ci.org/kosssi/ansible-role-apache.svg?branch=master)](https://travis-ci.org/kosssi/ansible-role-apache)

Install and configure apache.

## Role Defaults Variables

    apache_repository: false
    apache_ansible_ssl_path: "site_files/certificates" 
    apache_install:
      - apache2

    apache_module_disable: false
    apache_module_enable:
      - rewrite

    apache_site_disable:
      - 000-default
      - default-ssl
    apache_site_enable:
      - test.dev

    apache_vhosts:
      - servername: test.dev
        index: index.php
        document_root: /var/www/test
        document_root_options: -Indexes +FollowSymLinks
        directory_extra:
          - RewriteEngine On

## Example Playbook

    roles:
      - { role: kosssi.apache, tags: apache }

## License

Licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
