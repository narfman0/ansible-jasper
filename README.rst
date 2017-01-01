==============
ansible-jasper
==============

Ansible module for jasper project

Usage
-----

A vagrant file has been included for easier testing. To use::

    vagrant up

This will provision the machine such that a working jasper
is running! Some tweaks to sound devices may be needed.

TODO
----

* Fix libfst building, possibly make deb for faster deploy
* Get rest of jasper working; pausing maybe halfway now :)
* Deploy to ansible galaxy
* Augment documentation with raspberry pi+normal instructions
* Augment documentation for development with vagrant
* Deploy to raspberry pi (raspbian) via a small set of vars

License
-------

Please see included LICENSE file for license specifics

Copyright 2017 Jon Robison
