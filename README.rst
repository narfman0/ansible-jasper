ansible-jasper
==============

.. image:: http://img.shields.io/badge/ansible--galaxy-jasper-blue.svg
  :target: https://galaxy.ansible.com/narfman0/jasper/

Ansible module for jasper project.

Usage
-----


A vagrant file has been included for easier testing. To use::

    vagrant up

This will provision the machine such that a working jasper
is ready to run. Some tweaks to sound devices may be needed.

Raspberry pis need a few special tweaks, and some special
logic is reservered for them. To identify your device(s) as
raspberry pis, please but them in the `rasppi` group in e.g.
`/etc/ansible/hosts`.

Running playbook directly
~~~~~~~~~~~~~~~~~~~~~~~~~

I have a jasper host defined in `/etc/ansible/hosts`, that I
put in the rasppi group::

    [jasper]
    rasppi1

    [rasppi]
    rasppi1]


Assuming you have hosts identified (overriding playbook vars
or globally in `/etc/ansible/hosts`), you may invoke the
playbook directly with::

    ansible-playbook playbook.yml -v

Example
-------

Playbook::

    - hosts: servers
      vars_files:
        - vars/main.yml
      roles:
      - { role: narfman0.jasper }

Defaults use sphinx. If you want to use wit.ai, in `vars/main.yml`::

    jasper_witai_access_token = 'abcdefghijklmnopqrstuvwxyz'
    jasper_stt_engine = witai-stt


TODO
----

* Augment documentation

License
-------

Please see included LICENSE file for license specifics

Copyright 2017 Jon Robison
