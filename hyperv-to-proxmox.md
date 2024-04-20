# Migrate a Hyper-V VM to Proxmox

Had an old xubuntu VM running on Hyper-V which I wanted to migrate to my new Proxmox host and discontinue the old Hyper-V host. Couple of steps you need to execute to make this work.

* Get the .vhdx (hyper-v disk) file and move it to the Proxmox host (by using sftp)
* Create a new VM within Proxmox GUI with similar CPU and RAM specs as the old Hyper-V VM (no need to add a disk)
* From the Proxmox shell (I prefer direct SSH instead of Shell in the Proxmox GUI), import the .vhdx file in the newly created VM (set correct VM ID): ```qm disk import <VM-ID> /root/xubuntu.vhdx local-lvm```
* In the Proxmos GUI, set the BIOS of the new VM to OVMF (UEFI) and add a EFI Disk (through Add menu under Hardware)
* Boot the VM, great success!
