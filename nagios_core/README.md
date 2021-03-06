## Setup Guide

### Step 1: Clone Repository
Clone this repository

### Step 2: Add .tfvars file

```cd nagios_core```

Add **file.tfvars** file

```vi file.tfvars```

*Note: You need to provide values for the [vars.tf](vars.tf) file*

### Step 3 : Terraform 

Initialize Terraform

```terrafrom init ```

Validate Terraform file syntax

```terraform validate```

Generate Terraform Plan 

```terraform plan -var-file=file.tfvars```

Apply Terraform Code

```terraform apply -var-file=file.tfvars```

### Step 4 : Run Ansible Playbook

*Note: This step assumes the newly created nagios server is added as a managed host under your Ansible. Also it's added to the group "ansible-server". You can modify "hosts" line, based on your Ansible hosts file configuration.*

Edit hosts.yaml file

```vi hosts.yaml```

* Enter IP addresses of hosts that needs to be monitored by Nagios
* Edit :  line 12, line 22
* For addition hosts, add a new block under line 27

Run Ansible Playbook 

```ansible-playbook hosts.yaml```



For more information on how to add Ansible hosts visit - [Official Documents](https://docs.ansible.com/ansible/latest/user_guide/intro_inventory.html)