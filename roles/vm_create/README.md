## Role description

This role can be used to create a Linux VM running on top of a Nutanix hypervisor.

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

To specify in which cluster your VM will be created :

```yaml
cluster_name: home.lab
```

To set your VM's specs :

```yaml
vm_cpu: 2
vm_ram: 4
vm_template: template-rhel7-v1.0
```

By default, each VM is provisioned with 1 sockets / multiple cores.

To set your VM's network settings (one NIC only) :

```yaml
vm_ip: 192.168.3.111
vm_gateway: 192.168.3.254
vm_netmask: 255.255.255.0
vm_subnet_name: vlan555
vm_domain: home.lab
```

Managed and unmanaged networks can be used.

------

## Targets compatibility

This role has been tested on the following Nutanix versions :
- [x] Community Edition 20190916.276
- [x] 20201105.2229

------

## Usage

```bash
$ ansible-playbook playbooks/nutanix_vm_create.yml -i inventories/foo -l bar
```

------

## History

| 2021/11/10 | 1.0.1 | handle managed and unmanaged networks                     |
| ---------- | ----- | --------------------------------------------------------- |
| 2021/10/29 | 1.0.0 | initial release                                           |
