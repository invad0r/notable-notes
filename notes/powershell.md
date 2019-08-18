---
tags: [cli]
title: powershell
created: '2019-07-30T06:19:49.207Z'
modified: '2019-08-18T15:33:41.907Z'
---

# powershell

```sh
$myString = @"
	This is the first line
	of a very long string. A "here string"
	lets you to create blocks of text
	that span several lines.
	"@
```

```sh
# file Get-TimeResult.ps1
function Get-TimesResult {
  Param ([int]$a,[int]$b)
  $c = $a * $b
  Write-Output $c
}

# source file
. ./Get-TimeResult.ps1
Get-TimeResult -a 6 -b 8
```

```sh
Foo-Bar | Out-File docker.json -Append  #  write output to file
```

## cmdlets
```sh
alias
gal                     # alias: Get-Alias
[ gci | dir | ls ]      # alias: Get-ChildItem
```

command
```sh
get-command
gcm       # alias for get-command
gcm *get* # lists als command that contain get

Get-Command -PSSnapin snapin
```
https://www.youtube.com/watch?v=zps_3l0TQDY

## Snap-ins

* cmdlets are "packaged" in a snap-in (similar to ms-management-console: start->run->"mmc")
* multiple snap-ins can be loaded into the shell (Add-PSSnapIn)
* 120+ cmdlets provided by default snapins (Get-PSSnapin)

```
Get-PSSnapin

Get-Command -pssnapin Microsoft.PowerShell.Management       # list cmdlets from a perticular snapin
```

```sh
gcm           # get a list of cmdlets

get-process   # get a list of processes

get-service   # get a list of services

New-Alias     # create a new alias

New-Service   # create a new service
```

```
Get-ChildItem -path C:\Test*.txt -exclude "sample.txt"

# alias position and short parameter
Dir C:\Test*.txt -ex "sample.txt"
```

## vsphere
```sh
docker run --rm --name powercli -it --volume $(pwd):/usr/scripts vmware/powerclicore

PS /usr/scripts> cat ./connectVCenter.ps1
Set-PowerCLIConfiguration -InvalidCertificateAction Ignore -Scope Session

Connect-VIServer -Server vcenter1.domain.net    # login 
```

```sh
PS /usr/scripts> cat ./listVMsnapshots.ps1
Get-VM | Get-Snapshot | Select VM,Name,Description,@{Label="Size";Expression={"{0:N2} GB" -f ($_.SizeGB)}},Created |
Export-Csv 'results/aktive-snapshots.txt' -Encoding UTF8 -NoTypeInformation -Delimiter "|"

Get-Snapshot -vm * -name VEEAM BACKUP* | remove-snapshot  # remove backups snapshots
```

```sh
Get-VM -?   # get help

Get-VM -name * \
  |Select Name,@{N=’vNIC’;E={($_.ExtensionData.Config.Hardware.Device \
  | where{$_ -is [VMware.Vim.VirtualEthernetCard]}).Count}}
```
### Get full information about the VMs
```sh
Get-VM -name * \
  | Select Name,@{N=’vDisk’;E={($_.ExtensionData.Config.Hardware.Device \
  | where{$_ -is [VMware.Vim.VirtualDisk]}).Count}},@{N=’vNIC’;E={($_.ExtensionData.Config.Hardware.Device \
  | where{$_ -is [VMware.Vim.VirtualEthernetCard]}).Count}}, Notes, Guest, NumCpu, CoresPerSocket, MemoryGB, ResourcePool, UsedSpaceGB, ProvisionedSpaceGB

Get-VMHostNetworkAdapter \
  | select VMhost, Name, IP \
  | format-table -autosize

Get-VM | Select Name, @{N=”Cluster”;E={Get-Cluster -VM $_}}


Get-VM log \
  | Get-NetworkAdapter \
  | Select-Object @{N=”VM”;E={$_.Parent.Name}},@{N=”NIC”;E={$_.Name}},@{N=”Network”;E={$_.NetworkName}} \
  | ft -AutoSize

Get-Datastore | Select Name,@{N=’CanonicalName’;E={$_.Extensiondata.Info.Vmfs.Extent[0].DiskName}}
```
[day-to-day useful PowerCLi commands/scripts](https://arabitnetwork.com/2018/07/31/for-vmware-admins-day-to-day-useful-powercli-commands-scripts/amp/)
