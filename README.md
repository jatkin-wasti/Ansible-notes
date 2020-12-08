# Ansible
## What is Ansible
- Free and opensource
- Automation engine used for cloud provisioning, configuration management,
application deployment etc
- Uses easy to understand language (YAML or Yet Another Markup Language) that
is close to English
- Can improve scalability, consistency, and reliability of an IT environment

## Main parts of Ansible
**ansible.cfg**
- Holds configuration information
**inventory**
- holds the inventory of artifacts e.g. list of servers or nodes being managed
or configured
**variables.yml**
- holds the variables that are used to replace wildcards in your playbooks to
make them more reusable
**ec2_prov_playbook.yml**
- playbook that has list of tasks to provision an EC2 instance
**ec2_term_playbook.yml**
- playbook that has list of tasks to terminate an EC2 instance
**modules**
- units of codes used in playbooks to execute commands on remote servers, in a
key:value pair format
**plays**
- script/instruction defining a task to be carried out on a server. A collection
of plays makes up the playbook
**facts**
- system properties gathered by ansible while executing a playbook on a host
system. These could include hostname, OS, number and type of CPU cores

## How to provision one machine with Ansible
- Export your AWS key as an environment variable
- Install Ansible
- In ansible.cfg replace `${AWS_EC2_PEM_KEYPATH}` with the path to the key
- In variables.yml replace the wildcards listed below with the appropriate settings
`${ec2_region} ${ec2_tag_Type} ${ec2_image} ${ec2_keypair} ${ec2_volume_size} ${ec2_count} ${security_group_id} ${public_subnet_id} ${ec2_tag_Type} ${ec2_tag_Role}`
- cd into the directory with the prov playbook and run `ansible-playbook -v ec2_prov_playbook.yml`
- If you want to terminate the instance then run `ansible-playbook -v ec2_term_playbook.yml`
