

# About

Ansible role to install and configure Pi Camera on a Raspberry Pi .

# Usage

Drop the folders `picamera` and `top_level_handlers` into your `roles` directory
and add the following to your playbook (may vary depending on your setup):

  - hosts: pis
    roles:
      - picamera
    tags: picamera
    vars:
      - raspi_config_enable_camera: yes
      - raspi_config_memory_split_gpu: 16
      - raspi_config_min_camera_mem: 128
    gather_facts: true


# Works On

Tested on Raspbian Jessie on Pi B+.
