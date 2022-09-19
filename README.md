# Scrap-Metal (WIP)

Scrap-Metal is a hackable virtual machine manager for QEMU written in bash with minimal dependencies.


## Host

Scrap metal is built to run on AMD64 Ubuntu Server host machines. 
Support for other Debian-Based distros is a W.I.P 

GPU passthrough is supported for Intel CPU's and Nvidia GPU's ONLY.
This is because I don't have any AMD hardware, not because it isnt possible. 

The process for preparing the Host for GPU passthrough is best-effort, there are garunteed to be issues across hardware models and vendors. To minimize the chances of misconfiguration follow the full-process of re-imaging your host with the supported ISO.

### Helper scripts to configure the host:

`latest-kernel.sh`: downloads the latest ubuntu mainline kernel to the /tmp/new_kernel directory

`bridge.sh`: documents the full process for creating a bridged network and tap interface and the needed IPtables rules.

`bridge.conf`: file to allow netwok traffic over the bridge

`ip-tables.sh`: the required IPtables rules to allow bridged traffic

`tap.sh`: script to create a tap interface

`netplan config`: bridge host netplan config

`netplan config`: dynamic IP guest config

`netplan config`: static ip guest config

`governor.sh`: script to control CPU power states

`vmhost.sh`: get the PCI IDs of the GPU and alter grub and other config files to enable pass-
through
 

## Guest




Commands:
```bash
./vm.sh create-cloud-vm
./vm.sh boot-cloud-vm


./vm.sh create-from-iso <path-to-iso>
./vm.sh boot-iso-vm
  
./vm.sh create-windows-vm
./vm.sh boot-windows-vm
```
