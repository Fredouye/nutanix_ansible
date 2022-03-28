## Role description

This role can be used to take a snapshot of a (Linux / Windows) VM running on top of a Nutanix hypervisor.

It uses Nutanix REST API v2 (snapshots are currently not handled by the v3 REST API), and therefore can only be used with a Prisme Element.

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

An optional snapshot comment can be set :

```yaml
snapshot_comment: "Before OS update"
```

Otherwiwe, a default comment will be used.

------

## Targets compatibility

This role has been tested on the following Nutanix versions :
- [x] Community Edition 20190916.276

------

## Usage

```bash
$ ansible-playbook playbooks/nutanix_snapshot.yml -i inventories/foo -l bar
```

------

## History

| 2021/10/29 | 1.0.0 | initial release                                           |
| ---------- | ----- | --------------------------------------------------------- |
