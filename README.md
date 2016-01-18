Rancher OS iPXE script
======================

Allows quick provisioning of VirtualBox VM with Rancher OS.

Steps to set up:
  1. Clone this repository inside `~/.VirtualBox/TFTP` directory.
  2. Edit `cloud-config.yaml` and add your SSH key.
  3. Publish `cloud-config.yaml` on a remote server (GitHub Gist?).
  4. Edit `loader.ipxe` and specify absolute URL of `cloud-config.yaml`.
  5. Create new VM in VirtualBox and name it `Rancher` (add at least 1 GB of RAM).
  6. Configure the VM and on the `System/Motherboard` tab enable Network boot.
  7. Move Hard Disk in boot order to the top.
  8. Boot VM. Rancher OS will be installed on the Hard Drive.

VM name is important. Network boot will take the `~/.VirtualBox/TFTP/<VM>.pxe` file for booting.
See: https://www.virtualbox.org/manual/ch06.html#nat-tftp