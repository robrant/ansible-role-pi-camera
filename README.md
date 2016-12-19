

# About

Ansible role to configure a PiCamera on a Raspberry Pi.

# Dependencies

* A picamera, plugged into your raspberry pi via the picamera interface.

# Usage

**Folders:** Move folders as follows:

    $> cd ansible-role-pi-camera
    $> mv top_level_handlers /your_playbook/roles/
    $> mv library /your_playbook/
    $> mkdir -p /your_playbook/roles/picamera
    $> mv defaults /your_playbook/roles/picamera
    $> mv meta /your_playbook/roles/picamera
    $> mv tasks /your_playbook/roles/picamera

(or you can incorporate it into your repo using the `git submodule` commands).

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

Defaults and descriptions for the 3 vars can be found in `defaults/main.yml`.

# Example

[This repo](https://github.com/robrant/ansible-role-picamera-example-playbook.git) provides an example playbook that incorporates and runs this role.

# Works On

Tested on Raspbian Jessie on Pi B+. The variables are likely to need changing
for your Pi if your model is more recent than the B+.
