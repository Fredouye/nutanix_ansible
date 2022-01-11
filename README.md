Collection of Ansible roles to be used with a Nutanix AHV hypervisor :
- [vm_create](https://github.com/Fredouye/nutanix_ansible/tree/main/roles/vm_create) : creates a VM from a template.
- [vm_snapshot](https://github.com/Fredouye/nutanix_ansible/tree/main/roles/vm_snapshot) : takes a snapshot of a VM
- [vm_add_disks](https://github.com/Fredouye/nutanix_ansible/tree/main/roles/vm_add_disks) : adds disk(s) to an existing VM
- [vm_snapshots_remove](https://github.com/Fredouye/nutanix_ansible/tree/main/roles/vm_snapshots_remove) : removes all snapshots from a VM
- [vm_update](https://github.com/Fredouye/nutanix_ansible/tree/main/roles/vm_update) : updates specs of a VM
- [vm_delete] (https://github.com/Fredouye/nutanix_ansible/tree/main/roles/vm_delete): deletes a VM
- [image_upload](https://github.com/Fredouye/nutanix_ansible/tree/main/roles/image_upload) : uploads an image.


All these roles use the Nutanix REST API (version 3 for VM creation/deletion and image upload, version 2 for the others).

------

They require :
- a Prisme Element or Prisme Central instance
- access to the `TCP 9440` port of your Prism Element / Prism Central
- proper credentials.

------

REST API explorers are available for versions 2 and 3 :
- https://<prism_fqdn_or_ip>/api/nutanix/v2/api_explorer/index.html
- https://<prism_fqdn_or_ip>/api/nutanix/v3/api_explorer/

If you convert VM templates built on a VMWare hypervisor, make sure they include virtio drivers (and cloud-init, for OS customization).
