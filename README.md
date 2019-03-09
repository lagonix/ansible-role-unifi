Ansible Role: Unifi
=========

Installs Ubiquiti Unifi controller.

Requirements
------------

If you want to use your own certificate, you have to specify the *unifi_keystore_path:* variable and set *unifi_custom_certificate:* to true.

Role Variables
--------------

Available variables are listed below,

    unifi_custom_certificate: false

Set to true if you want to replace the keystore with your own.

    unifi_keystore_path: ''

Specify path to keystore if you want to replace the default certificate.

    unifi_keystore_remote_path: '/var/lib/unifi/keystore'

Specify where to place the keystore, currently set to unifi default.

    apt_key_server: 'hkp://keyserver.ubuntu.com:80'

Specify keyserver to use.

    unifi_apt_repo: 'deb http://www.ui.com/downloads/unifi/debian stable ubiquiti'

Specify unifi apt repository.

    unifi_apt_repo_filename: '100-ubnt-unifi'

Specify unifi apt repository filename.

    unifi_mongodb_apt_repo: 'deb http://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/3.4 multiverse'

Specify mongodb apt repository.

    unifi_mongodb_apt_repo_filename: 'mongodb-org-3.4'

Specify mongodb apt repository filename.

    unifi_apt_key_server: '{{ apt_key_server }}'

Set key server for unifi task to apt_key_server.

    unifi_apt_key_id: '06E85760C0A52C50'

Specify current unifi gpg key id.

    unifi_mongodb_apt_key_server: '{{ apt_key_server }}'

Set key server for mongodb task to apt_key_server.

    unifi_mongodb_apt_key_id: '0C49F3730359A14518585931BC711F9BA15703C6'

Specify current mongodb gpg key id.

    unifi_prerequisites:
        - apt-transport-https

Specify list of prerequisites.

    unifi_package_name: unifi

Specify unifi package name.

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: mrleerkotte.unifi }

License
-------

BSD-3

Author Information
------------------

This role was created in 2019 by [Marlon Leerkotte](https://linkedin.com/in/marlonleerkotte).
