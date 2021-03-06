![Pulp CI](https://github.com/pulp/pulp_rpm_prerequisites/workflows/Pulp%20CI/badge.svg)

Pulp 3 RPM plugin prerequisites
===============================

This role installs prerequisites for pulp-rpm plugin use, when installed by
pulp_installer.

Requirements
------------

Each currently supported operating system has a matching file in the "vars"
directory.

Installation
------------

Install in the [ansible role search path](https://docs.ansible.com/ansible/latest/user_guide/playbooks_reuse_roles.html#role-search-path)
as the foldername `pulp.pulp_rpm_prerequisites`, by either:
*. `ansible-galaxy install pulp.pulp_rpm_prerequisites -p ./roles/`
*. Cloning this repo, and symlinking it as pulp.pulp_rpm_prerequisites

Example Playbook
----------------

Here's an example playbook for using pulp_rpm_prerequisites as part of pulp_installer.

    ---
    - hosts: all
      vars:
        pulp_default_admin_password: password
        pulp_settings:
          secret_key: secret
        pulp_install_plugins:
          pulp-rpm:
            prereq_role: "pulp.pulp_rpm_prerequisites"  # https://galaxy.ansible.com/pulp/pulp_rpm_prerequisites
      roles:
        - pulp_database
        - pulp_workers
        - pulp_resource_manager
        - pulp_webserver
        - pulp_content
      environment:
        DJANGO_SETTINGS_MODULE: pulpcore.app.settings

License
-------

GPLv2+

Author Information
------------------

Pulp Team
