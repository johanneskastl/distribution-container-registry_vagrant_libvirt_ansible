# distribution-container-registry_vagrant_libvirt_ansible

This Vagrant setup creates a VM and sets up the
[distribution container registry](https://github.com/distribution/distribution).

This is the Open Source Registry implementation for storing and distributing
container images and other content using the OCI Distribution Specification. The
goal of this project is to provide a simple, secure, and scalable base for
building a large scale registry solution or running a simple private registry.
It is a core library for many registry operators including Docker Hub, GitHub
Container Registry, GitLab Container Registry and DigitalOcean Container
Registry, as well as the CNCF Harbor Project, and VMware Harbor Registry.

Default OS is openSUSE Tumbleweed. Although that can be changed in the
Vagrantfile, please beware that this will break the Ansible provisioning.

## Vagrant

1. You need vagrant obviously. And ansible. And git...
1. Fetch the box, per default this is `opensuse/Tumbleweed.x86_64`, using
   `vagrant box add opensuse/Tumbleweed.x86_64`.
1. Make sure the git submodules are fully working by issuing `git submodule init
   && git submodule update`
1. Run `vagrant up`
1. Log in using `vagrant ssh` and check the service status using `systemctl
   status distribution-container-registry.service`. The default configuration
   logs dummy logs to the systemd journal, you can check using `sudo journalctl
   -flu distribution-container-registry.service`.
1. Party!

## Cleaning up

The VMs can be torn down after playing around using `vagrant destroy`.

## License

BSD-3-Clause

## Author Information

I am Johannes Kastl, reachable via git@johannes-kastl.de
