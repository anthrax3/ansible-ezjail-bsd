# 1. Install Ansible on Free BSD as follows
# ssh to the remote system where you are setting up jails)

  ssh username@remote-freebsd-server.com

# and then execute the below
  pkg install lang/python
  pkg install ansible

  Ansible version should be >=2.2.0.0

# 2. Grab a copy of the latest source repository

If you are not a collaborator on the source repo at bitbucket, you can ask for a shared zip file. Collaborators can clone as below:
  su #Switch to root
  cd /root
  git clone https://sureronald@bitbucket.org/sureronald/ansible-ezjail-bsd.git

If you already have the repository you can run 'git pull' to update to the latest source code

# 3. Run the ezjails playbook as follows

  cd ansible-ezjail-bsd/
  ansible-playbook ezjail.yml -vvvv -i inventories/inventory.prod -c local

 Note that we are running the playbook locally and configuring the host
 NB: If you are using your own inventory, ensure it has a [jails] section

# 4. Debugging
Run the ansible-playbook command as follows to run specific parts. Note that the 'setup' tag has to be included since we have set gather_facts to 'no' in the playbook. We gather facts in the playbook later on.

   ansible-playbook ezjail.yml -vvvv -i inventories/inventory.prod --tags="setup,ezjailadmin" -c local
