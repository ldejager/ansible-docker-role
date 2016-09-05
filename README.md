# Ansible Docker Playbook

Install docker onto RHEL based host from the official repositories and setup the device mapper storage driver.

## Configuration items

- `docker_storage_type` - Can either be `image` or `disk`. The image based storage setup acts as a workaround Digital Ocean where you get assigned a single disk drive. A new volume feature is currently in beta and available in limited datacenters but once it's GA, this playbook can be refactored.
- `docker_storage_device` - Path to the device, i.e. `/dev/docker_storage0` when using a loop device to mount the file based image as a block device.
- `docker_storage_location` - Path on disk for the image, i.e. `/docker`.
- `docker_storage_size` - Size of the image, i.e. `20480` for a 20GB image.

## Using

Example Playbook

```
- hosts: all
  roles:
    - docker
```
