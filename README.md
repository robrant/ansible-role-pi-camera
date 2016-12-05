

# About

Ansible role to install and configure Pi Camera on a Raspberry Pi .

# Dependencies

* A picamera, plugged into your raspberry pi via the picamera interface.

# Usage

**Folders:** Drop the folders `picamera` and `top_level_handlers` into the `roles` directory
of your playbook. Drop the `library` directory into your playbook top-level
(alongside your `roles` directory).

**Define Play**. Add the following to your playbook (YMMV):

  - hosts: pis
    roles:
      - picamera
    tags: picamera
    vars:
      - raspi_config_enable_camera: yes
      - raspi_config_memory_split_gpu: 16
      - raspi_config_min_camera_mem: 128
    gather_facts: true

Defaults and descriptions for the 3 vars can be found in `picamera/defaults/main.yml`. 

# Works On

Tested on Raspbian Jessie on Pi B+. The variables are likely to need changing
for your Pi if your model is more recent than the B+.
