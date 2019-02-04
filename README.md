OpenTelekomCloud Keypair role
=============================

A quick role to create KeyPair in OTC and save private key locally.

Requirements
------------

It is required, that openstacksdk is installed on the execution host and connection to the OTC is provided.

Role Variables
--------------

Available variables are listed below, along with default values (see `defaults/main.yml`):
  # Prefix for the resources
  # prefix: test-

  # Keypair name
  # keypair_name: "{{ (prefix + 'KeyPair') }}"

  # Location for the private key to be stored to
  # keypair_private_key_dest: "{{ '~/.ssh/keypair.pem' }}"

  # set this to force key deletion
  force_delete_key: false

  # State (`present` for creation, `absent` for deletion)
  state: present


Dependencies
------------

None.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: localhost
      roles:
         - otc_keypair

Cleanup of the keypair is as easy, as it's creation. For that a variable 'state': 'false' should be passed:

    - hosts: localhost
      roles:
        - { role: otc_keypair, state: 'absent'}

If a private key should be also deleted, a variable `force_delete_key` should be set.

License
-------

Apache


Author Information
------------------

OpenTelekomCloud
