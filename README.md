# ansible-docker-registry
Ansible playbooks to build a private Docker Registry.

This Ansible project builds a private Docker Registry outlined in this [article](https://phoenixnap.com/kb/set-up-a-private-docker-registry)

I wrote this as a learning project for Ansible, and I also need a private Docker registry on a virtual machine from some other learning I am doing.

This is intended to be run on a bare Ubunto Virtual machine. I have included a Vagrantfile if you wish to use VirtualBox. Personally, I deploy it onto my proxmox cluster.

# Requirements
1. Ansible installed on the machine that you cloned this repo to. (the "controller")
2. A  standard Ubuntu machine with python installed. You must be able to reach the VM by hostname or ip from the machine you are running Ansible on.
3. An account on the VM for Ansible to use. The account should be able to run sudo without requiring the root password. If you need to use sudo authentication, you can specify the password in the ansible or ansible-playbook command lines using the --ask-become-pass or -K option. The account should have your "controller" machine's SSH public key installed in the account's `authorized-keys` file (by either manually copying or using `ssh-copy-id` from your machine).
4. To confirm everything is ok, create an `inventory` file  with your host and asnible_user and place it in the `playbook` folder of the project. From that playbook folder, run `ansible all -m ping` to confirm your config. It should look like 
```
[server]
your-host-name ansible_user=your_user
```

