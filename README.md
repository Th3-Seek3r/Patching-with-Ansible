# Patching-with-Ansible
Run the Playbook:
$ ansible-playbook update_nginx.yml --ask-become-pass

N:B- If it asks for BECOME password, please type your kali password

Check for the updated/latest version of nginx after patching with Ansible:
$ nginx -version
