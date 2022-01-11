## Role description

This role can be used to upload images (ISO or disks images) to your Nutanix hypervisor.

It uses Nutanix REST API v3.

------

## Prerequisites

Access to the `TCP 9440` port of your Prism Element / Prism Central.

------

## Input variables

You need to declare the FQDN or IP address of your Prism Element / Prism Central, and your credentials.

```yaml
prism_url: 192.168.3.245
prism_user: admin
prism_password: ********
```

Sensitive credentials should be stored in an Ansible vault.

Images can be of 2 types :

- ISO

```yaml
image_name: centos7
image_description: "7.9"
image_type: ISO_IMAGE
image_url: http://centos.mirror.fr.planethoster.net/7.9.2009/isos/x86_64/CentOS-7-x86_64-NetInstall-2009.iso
```

- "disk" images (VMDK, QCOW2, etc.)

```yaml
image_name: CentOS-8.5-v1.0
image_description: "v1.0 from 2022/01/09"
image_type: DISK_IMAGE
image_url: http://192.168.3.250/packer/CentOS/T-centos8.5-v1.0.qcow2
```

------

## Targets compatibility

This role has been tested on the following Nutanix versions :
- [x] Community Edition 20190916.276
- [ ] 20201105.2229

------

## Usage

```bash
$ ansible-playbook playbooks/nutanix_image_upload.yml
```

------

## History

| 2021/12/28 | 1.0.0 | initial release                                           |
