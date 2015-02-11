uchiwa
========

Ansible role to install uchiwa.

Requirements
------------

Tested on Anbsible 1.8

Role Variables
--------------
    uchiwa_online_install: true                        # Whether or not to perform an online installation by downloading the installer
    uchiwa_installer_path: /tmp/uchiwa-0.4.1-1.x86_64.rpm # Where to find the installer for an offline installation
    uchiwa_version: 0.4.1-1                            # The version of uchiwa to install
    uchiwa_architecture: x86_64                        # The architecture (i386|x86_64)
    uchiwa_sensu_name: sensu                           # Name of the Sensu API
    uchiwa_sensu_host: localhost                       # Hostname/IP of Sensu server
    uchiwa_sensu_port: 4567                            # Port the Sensu API listens on 
    uchiwa_sensu_ssl: false                            # Use SSL to talk to Sensu API 
    uchiwa_sensu_insecure: false                       # Accept insecure certificates
    uchiwa_sensu_path:                                 # Path of Sensu API (empty for none) 
    uchiwa_sensu_timeout: 5                            # Timeout for Sensu API in seconds
    uchiwa_sensu_user: admin                           # Username for Sensu API (empty for none)
    uchiwa_sensu_password: secret                      # Password for Sensu API (empty for none)
    uchiwa_host: 0.0.0.0                               # IP which Uchiwa will listen on 
    uchiwa_port: 3000                                  # Port Uchiwa will listen on
    uchiwa_user:                                       # Uchiwa user (empty for none)
    uchiwa_password:                                   # Uchiwa password (empty for none)
    uchiwa_refresh: 5                                  # Interval to pull from the Sensu API
    uchiwa_healthcheck_file:                           # File to return as response to healthcheck
    uchiwa_healthcheck_content:                        # Content of http response
    uchiwa_htpasswd_files_path:                        # Where to find uchiwa.htpasswd
    uchiwa_purge_htpasswd: false                       # Delete htpasswd files 
    uchiwa_web_users:                                  # List of user hashes with read access (Requires python-passlib)
      guest:
        username: guest
        password: password

Dependencies
------------

nginx # Calls 'restart nginx' handler when configuration is created or modified

Example Playbook
-------------------------

    - hosts: all
      sudo: yes
      roles:
         - nginx
         - uchiwa

License
-------

MIT

Author Information
------------------

Jon Hadfield
