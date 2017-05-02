bbaassssiiee.artifactory
=========

Install Artifactory, the Maven repository manager by JFrog.

Requirements
------------

This role was built for RedHat systems like RHEL 6, Centos 6. It needs Java, and PostgreSQL or MySQL.

Role Variables
--------------
artifactory_database can hold either 'mysql' or 'postgresql', you should provide the database yourself now,
it is no longer a transitive dependency.

artifactory_password is defined in defaults/main/yml, override it in group_vars.

artifactory_version is defined in vars/main.yml
Set JAVA_OPTIONS in templates/etc-opt-jfrog-artifactory-default.j2

Dependencies
------------

Artifactory needs Java and either PostgreSQL or MySQL. I tested this role with Java by geerlingguy and MariaDB by pcextreme.

ansible-galaxy install -p roles pcextreme.mariadb
ansible-galaxy install -p roles geerlingguy.java

Example Playbook
----------------
For a complete example with this role check out my buildserver:
git clone https://github.com/bbaassssiiee/buildserver.git

Example of how to use this role:

    - hosts: servers
      roles:
         - { role: bbaassssiiee.artifactory }

License
-------

BSD,MIT

Author Information
------------------
Bas Meijer @bbaassssiiee
