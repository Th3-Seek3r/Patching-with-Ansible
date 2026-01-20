# Patching-with-Ansible
Patching nginx with ansible

> To install Ansible
$ sudo apt install ansible -y
> Check the current version
$ ansible --version

> Ansible update yml script
> nano update_nginx.yml
"
- name: Patch Nginx on Kali Linux
  hosts: localhost
  become: yes

  tasks:
    - name: Remove outdated Nginx (if installed manually)
      file:
        path: /usr/local/nginx
        state: absent

    - name: Ensure system package lists are updated
      apt:
        update_cache: yes

    - name: Install latest Nginx
      apt:
        name: nginx
        state: latest

    - name: Start and enable Nginx service
      systemd:
        name: state: started
        enabled: y
  "

> updating the patch with the script
$ ansible-playbook update_nginx.yml --ask-become-pass

#to check for the current version
$ nginx -version
