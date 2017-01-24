# vagrant-dev
Vagrant and Ansible configurations for isolated dev environments.
See https://help.github.com/articles/duplicating-a-repository/ for steps to
copy this repo (untracked) for use in a new project.

### The Vagrant machine:
* syncs app_dir/ on the host with /var/www/django-app on the guest
* is configured to have a local address of 192.168.33.10

### The Ansible configuration consists of:
* a main vagrant.yml that is run when Vagrant machine is started/reprovisioned, which runs the below
* a 'deploy' directory, which contains OS-level setup config, such as packages and the virtual environment
* a 'setup' directory, which contains project setup config (Python packages, dev DB user setup, etc.)

# Using the VM

`vagrant up` - bring the environment up.  Needs to be run from the project root (where Vagrantfile should live)

`vagrant suspend` - suspend the machine, saving state (frees RAM on disk and doesn't use CPU)

`vagrant destroy` - stop the machine and free all resources

`vagrant provision` - re-run any provisioning without needing to bring the machine down

See the [Vagrant CLI docs](https://www.vagrantup.com/docs/cli/)

# Installation

* [Install Vagrant](https://www.vagrantup.com/docs/installation/)
* Vagrant requires [VirtualBox](https://www.virtualbox.org/) on your machine
* If anything complains about missing box or OS image, run `vagrant box add ubuntu/trusty64`
