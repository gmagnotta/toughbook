# Reliable and Secure Automation at the Edge DEMO

Demo to show how to automate air gapped edge devices in a secure way

The idea is to use a secure laptop such as the Panasonic Toughbook as the trusted
environment that is installed and configured in the core and then used in the field
to automate the edge configuration

## Prerequirements

- Install Red Hat Device Edge on the edge system
- Allow ssh authentication to the root user with an ssh key
- Put the ip address of Red Hat Device Edge in inventory file
- Execute setup_microshift.yaml with ansible
- Install Red Hat Enteprise Linux on the toughbook
- Create an user and enable ssh key authentication for the user
- Allow the user to use sudo without password:

put a file /etc/sudoers.d/<user>

with content:

<user>	ALL=(ALL)	NOPASSWD: ALL

- Configure inventory with the ip address of the toughbook

## Simulate the Core Automation
- Execute setup_toughbook.yml to configure the toughbook
- After the playbook termination the toughbook is ready to be plugged in the air gapped network

## Simulate the Edge Automation
- Execute deploy_application.yml to configure the edge device
- After the playbook termination the edge device is configured and running the hello-tomcat application


