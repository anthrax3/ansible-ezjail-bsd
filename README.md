# 1. Install Ansible
  install from packages, grab the latest copy from github or on a python virtualenv

# 2. Configure SSH passwordless login to an account on the remote server.
# 3. Install Python. It is required by Ansible
  ansible -i inventories/jails.yml -K --become --become-method=su -m raw -a 'pkg install python' jails

# 4. Run the ezjails playbook as follows
  ansible-playbook ezjail.yml -i inventories/jails.yml -K

  You will be prompted to enter the 'su' password

  NB: Edit the inventories/jails.yml to match your hosts
