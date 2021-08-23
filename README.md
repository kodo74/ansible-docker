# Notes
Testing and development was done on Debian 11 (no GUI).  The `ansible_user` should be able to sudo on the machine running the code.  This code should work on Ubuntu/RHEL/CentOS but it wasn't tested with those environments.  This code also assumes that the software listed below is installed on the host running the code.  Versions used can be found below as well.

# Tools Installed via OS Package Manager
* ansible v2.10.8
* docker-ce v20.10.8

# Tools Installed via Ansible Automation
* python3-pip
* psycopg2-binary Python3 Package

# How To Run
1. Copy this code onto an instance that meets the above criteria
2. Go into the ansible-docker/ansible/ directory
3. Edit the `ansible_user` value in the group_vars/all.yml file to reflect the user on your system that has sudo privileges
3. Run the command below.  Make sure to change the `ansible_become_pass` to the password of the `ansible_user` mentioned above.  Additionally, you may change the `postgres_password` if desired

`ansible-playbook deploy-test.yml --extra-vars "ansible_become_pass=XXXXXXXX postgres_password=password1234"`
