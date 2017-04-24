=============================
Configuring for a new project
=============================

Configuring for Django + Postgres
=================================

Once Vagrant is installed, clone or copy the Vagrantfile and provision/ directory to the project root, and start by changing the following;

provision/vm/tasks/main.yml:

* 'Install packages' directive, listing any system-level packages to be installed

provision/app/vars/main.yml:

* 'project_name' declration
* 'python_version' declaration (3.4 by default)
* 'app_env': 'DJANGO_SETTNGS_MODULE' declaration (or any app-related environment variables to set)


When provisioning (``vagrant provision``), requirements.txt should be in the project root (same level as Vagrantfile, provision/ directory)
