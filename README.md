Ansible Role: Customize ESXi
=========

Waits for customization to complete and customizes the SSH configuration for ESXi hosts.

Requirements
------------

None.

Role Variables
--------------

None.

Dependencies
------------

None

Example Playbook
----------------

    # ===========================================================================
    # Customize ESXi
    # ===========================================================================
    - name: Customize ESXi
      hosts: vmware
      gather_facts: false
      tags: play_create_npod

      vars_files:
        # Ansible vault with all required passwords
        - "../../credentials.yml"

      vars:
        ansible_python_interpreter: /bin/python
        # Specifying the ansible_password variable to avoid password prompt or '-k' flag
        ansible_password: "{{ vault_esxi_password }}"

      roles:
        - ansible-role-vmware-customize-esxi


License
-------

MIT

Author Information
------------------

Aaron Patten
aaronpatten@gmail.com
