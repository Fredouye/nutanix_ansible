## Role description

This role can be used to take a add disk(s) to a Linux / Windows VM running on top of a Nutanix hypervisor.

It uses Nutanix REST API v2 (VMs disks are currently not handled by the v3 REST API), and therefore can only be used with a Prisme Element.

------

## Prerequisites

Access to the `TCP 9440` port of your Prism **Element**. 

------

## Input variables

You need to declare the FQDN or IP address of your Prism Element / Prism Central, and your credentials.

```yaml
prism_url: 192.168.3.245
prism_user: admin
prism_password: ********
```

Sensitive credentials should be stored in an Ansible vault.

To add disk(s) :

```yaml
vm_disks_list:
  - 20
  - 50
```

By default, thin provisioning is used, but you change the behaviour :

```yaml
vm_disk_thin: false
```

------

## Targets compatibility

This role has been tested on the following Nutanix versions :
- [x] Community Edition 20190916.276

------

## Usage

```bash
$ ansible-playbook playbooks/nutanix_add_disk.yml -i inventories/foo -l bar
```

------

## History

| 2021/10/29 | 1.0.0 | initial release                                           |
| ---------- | ----- | --------------------------------------------------------- |
