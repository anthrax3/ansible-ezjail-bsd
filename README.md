# 1. Install Ansible
  install from packages, grab the latest copy from github or on a python virtualenv
  Ansible version should be >=2.2.0.0

# 2. Configure SSH passwordless login to an account on the remote server.

# 3. Run the ezjails playbook as follows
  ansible-playbook ezjail.yml -i inventories/inventory.prod -K

  You will be prompted to enter the 'su' password

  NB: Edit the inventories/jails.yml to match your hosts

# 4. Debugging
Run the ansible-playbook command as follows to run specific parts. Note that the 'setup' tag has to be included since we have set gather_facts to 'no' in the playbook. We gather facts in the playbook later on.

   ansible-playbook ezjail.yml -vvvv -i inventories/inventory.prod --tags="setup,ezjailadmin" -K
