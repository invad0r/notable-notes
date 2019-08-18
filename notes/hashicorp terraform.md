---
tags: [cli, iac]
title: hashicorp terraform
created: '2019-07-30T06:19:49.078Z'
modified: '2019-08-18T15:02:01.111Z'
---

# hashicorp terraform

```
resource TYPE NAME {
    CONFIG ...
    [count = COUNT]
    [depends_on = [NAME, ...]]
    [provider = PROVIDER]
    [LIFECYCLE]
    [CONNECTION]
    [PROVISIONER ...]
}
```
[Configuring Resources - Terraform by HashiCorp](https://www.terraform.io/docs/configuration/resources.html#syntax)


```json
resource "vsphere_file" "photon_disk_upload" {     
  datacenter = "some Datacenter"                        
  datastore = "datastoreX"                         
  source_file = "./photon-ova-disk1.vmdk"          
  destination_file  = "/ISO-Images/photon-ova-disk1.vmdk"                                             
} 
```

### check state
```sh
terraform state list

terraform state show module.path.data.vsphere_virtual_machine.template
```

### format configuration
```sh
terraform fmt -diff -check  main.tf
```
