# Patching-with-Ansible

This repository demonstrates how to patch **Nginx** on a Kali Linux system using **Ansible**.

## Prerequisites

* Kali Linux
* Ansible installed
* Sudo (become) privileges
* An existing Ansible playbook named `update_nginx.yml`

---

## Run the Playbook

The playbook file **`update_nginx.yml`** is included in this repository.

Execute the following command to run the Ansible playbook:

```bash
ansible-playbook update_nginx.yml --ask-become-pass
```

**Note:**
If prompted for the **BECOME password**, enter your **Kali Linux user password**.

---

## Verify Nginx Version

After the playbook completes successfully, verify that Nginx has been updated to the latest version:

```bash
nginx -version
```

This command will display the installed Nginx version, confirming that the patching process was successful.

---

## Outcome

* Outdated Nginx (if present) is removed
* Latest Nginx package is installed via APT
* Nginx service is enabled and running
