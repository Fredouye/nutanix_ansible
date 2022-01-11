## Role description

This role can be used to delete a Linux / Windows VM running on top of a Nutanix hypervisor.
If multiple VMs with the same name are found, they're all deleted.

It uses Nutanix REST API v3.

------

## Prerequisites

Access to the `TCP 9440` port of your Prism Element / Prism Central.

OS customization is done using cloud-init, your template needs to include this package.

------

## Input variables

You need to declare the FQDN or IP address of your Prism Element / Prism Central, and your credentials.

```yaml
prism_url: 192.168.3.245
prism_user: admin
prism_password: ********
```

Sensitive credentials should be stored in an Ansible vault.

------

## Targets compatibility

This role has been tested on the following Nutanix versions :
- [x] Community Edition 20190916.276
- [ ] 20201105.2229

------

## Usage

```bash
$ ansible-playbook playbooks/nutanix_vm_delete.yml -i inventories/foo -l bar
```

------

## History

| 2022/01/11 | 1.0.0 | initial release                                           |
| ---------- | ----- | --------------------------------------------------------- |
