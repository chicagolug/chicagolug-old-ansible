user_account
============

Role to create a user account on a remote system.

Requirements
------------

Developed and tested using Ansible 2.3.2.

Role Variables
--------------

- user_name: kept in defaults/main.yml
- user_password: kept in vars/main.yml

The password is created using Ansible Vault. You'll need to encrypt an actual
password hash, and not the password itself.

Here is an example:

echo '$6$wk4567yOb$YkKNBYQgPlfYH.gLgVFrkVpN56L/EoruEdjZMphRO74Xlj0RGLYR5McZzKRO0pUo6rnD.X7GkHBrxrQs8928t.' | ansible-vault encrypt_string --stdin-name 'user_password'

Dependencies
------------

None

Example Playbook
----------------

    - hosts: all
      user: root 
      roles:
         - { role: user_account, tags: ["user_account"] }

License
-------

CC0

Author Information
------------------

Jim Campbell (jcampbell@gnome.org)
