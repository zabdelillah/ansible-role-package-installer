package-installer
=========

Automates package installs across distributions further than the standard package
task, adding repositories to the system and pre-configuring installations where
needed from variables.

Requirements
------------

None

Role Variables
--------------

`system_packages (list[str])`: packages to install to the system
`pip_packages (list[str])`: packages to install into the system python path

`apt_repositories (list[str])`: adds repositories for apt (Debian) to find
`custom_repositories (dict)`: -
`custom_repositories[*].from_deb (str)`: installs a repository from the given debian file

`package_configuration (dict)`: provides automatic configuration of packages
`package_configuration[*].package (str)`: package to configure
`package_configuration[*].question (str)`: question key
`package_configuration[*].value (str)`: answer
`package_configuration[*].value_type (str)`: format of the answer

Dependencies
------------

-

Example Playbook
----------------

```
- hosts: all
  roles:
    - version: main
      name: zabdelillah.ansible-role-package-installer
      vars:
        system_packages:
          - python3
        apt_repositories:
          - https://packages.ubuntu.com/ noble
        python_packages:
          - boto3
```

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
