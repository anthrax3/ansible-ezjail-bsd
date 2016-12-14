# 1. Install Ansible
  install from packages, grab the latest copy from github or on a python virtualenv
  Ansible version should be >=2.2.0.0

# 2. Configure SSH passwordless login to an account on the remote server.

# 3. Run the ezjails playbook as follows
  ansible-playbook ezjail.yml -i inventories/inventory.prod -K

  You will be prompted to enter the 'su' password

  NB: Edit the inventories/jails.yml to match your hosts
