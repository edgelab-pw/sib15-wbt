# SIB15 WBT - Ubuntu 14.04 minimal Vagrant Box

**Current Ubuntu Version Used**: 14.04.4

This example build configuration installs and configures Ubuntu 14.04 x86_64 minimal using Ansible, and then generates two Vagrant box files, for:

  - VirtualBox
  - VMware

The example can be modified to use more Ansible roles, plays, and included playbooks to fully configure (or partially) configure a box file suitable for deployment for development environments.

## Requirements

The following software must be installed/present on your local machine before you can use Packer to build the Vagrant box file:

  - [Packer](http://www.packer.io/)
  - [Vagrant](http://vagrantup.com/)
  - [VirtualBox](https://www.virtualbox.org/) (if you want to build the VirtualBox box)
  - [VMware Fusion](http://www.vmware.com/products/fusion/) (or Workstation - if you want to build the VMware box)
## Usage

Copy the Vagrantfile to your local machine, then cd to the directory containing the file and run:

	$ vagrant up --provider virtualbox

## Building with Packer 

Make sure all the required software (listed above) is installed, then cd to the directory containing this README.md file, and run:

    $ packer build sib15-wbt-local.json

After a few minutes, Packer should tell you the box was generated successfully.

If you want to only build a box for one of the supported virtualization platforms (e.g. only build the VMware box), add `--only=vmware-iso` to the `packer build` command:

    $ packer build --only=vmware-iso sib15-wbt-local.json

## License

MIT license.

## Author Information
Modified in 2016 by [Vinzenz Stadtmueller](https://www.edgelab.pw)
Created in 2014 by [Jeff Geerling](http://jeffgeerling.com/), author of [Ansible for DevOps](http://ansiblefordevops.com/).
