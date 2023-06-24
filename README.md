# learn-ansible

# roboshop-ansible

##Ansible supports push and pull
##Ansible uses ssh connection
##Ansible uses some inventory file
## The same script that we kept in a file for bash script is the same script that we will provide in ansible
#playbook and the play book should be written in a mark up languange

##Ansible play book is written in keys and value pair
#Mark up language are written in 3 format Plain. List and  Map/dictionary

Yaml is simple key value map
In yaml indentation is very key

#Example of plain
## a: = 10

#Examples of list
## b: [ 99,89 ]
## b:
#  - 99
#  - 89

#Examples of Map
# c:
course: DevOps
time: 730am

# c: { Course: DevOps,
# time: 7:30am }

# Ansible is expecting the inputs in yaml
# keys are provided by ansible and we need to refer to the documentation
# keys are called parameters and provided by ansible
# some values are also provided by ansible
# Ansible will provide the keys and the value and you tell ansible what you want to do
# If you are installing a package you have to tell ansible what package you are installing
# You have to open the documentation , read it understand and implement it

# How to write a playbook
name: Some Playbook
hosts: all
tasks:
- name: Demo Tasks
  ansible.builtin.yum:
  name: nginx
  state: installed

- name: Some role play
  hosts: all
  roles:
    - demo


# The name is a key word provided by ansible and we are giving our value some playbook
# hosts is a key word provided by ansible and we give our value all
# tasks is a key word provided by ansible
# We provide the name (demo task) and module (ansible.builtin.yum)
# name (nginx) provided by ansible
# state (installed) provided by ansible

# file extension can be .yml or .yaml

## sample.yaml is a playbook
 every playbook starts with a list with a hyphen and it can have one or more plays
 name keyword on play is optional and good to have
 The hosts is must to have, that is which hosts to connect
 Either task/roles is a must to have role


##Install Ansible   

##In the workstation server - sudo labauto ansible

## syntax = ansible-playbook -i 172.31.84.198, -e ansible_user=centos -e ansible_password=DevOps321 01-sample.yml
## ansible-playbook -i /tmp/inv -e ansible_user=centos -e ansible_password=DevOps321 01-sample.yml

/tmp/inv
172.31.86.105
[web]
172.31.86.105
172.31.86.103

## -i = inventory
## -e = 
## private ip address of the ansible
## sample.yml is our file that contains our config
## we can also use file path as inventory, you provide the path where you have added all your ip addresses in vi e.g. -i /tmp/inv
## if you are providing direct server ip address instead of a file path you will use a comma
# we provide the root server to connect to, how to connect and what to do when connected, it just connects to the node and do the job, here
## it will just print "hello world"


##Creating an Ansible playbook is a straightforward process. First, 
#you need to create a YAML file and define hosts, variables, tasks, and handlers. 


An Ansible playbook is composed of four main components −

Hosts − target hosts on which tasks will be executed. Hosts can be defined using IP addresses,
hostnames, or patterns that match groups of hosts.

Variables − Variables define data used by tasks in a playbook. Variables can be defined 
at playbook level or at task level. They can also be set as defaults or overridden on a per-host or per-group basis.

Tasks − Tasks define actions to be executed on target hosts. Tasks can be composed of modules,
which are pre-built Ansible scripts that perform specific functions such as managing files, installing packages, or restarting services.

Handlers − Handlers define actions to be executed in response to events triggered by tasks. 
Handlers are similar to tasks but are only executed if they are notified by a task. Handlers can be used, 
for example, to restart a service only if it has been changed by a task.

Roles
Roles allow you to organize your playbooks into reusable units of work. 
Roles contain tasks, handlers, variables, and files that are specific to a particular 
function or application. Roles can be shared and reused across multiple playbooks. 

To  get anything in ansible you have to use the documentation or go to google straight and you go down and find the example 
and make sure you use the indentation
Install yum package ansible module
sudo in ansible playbook
how to run ansible as sudo

## Ansible playbook is a push command and thats why we logging in to the workstation and using ansible-playbook command to push the 
codes to the node 

You can login to the node system and pull the command too using the ansible-pull command

##Syntax and description: 
#ansible supports the pull command called ansible-pull
local host is a dns record of the local system
url of your code - https://github.com/favorgithub/learn-ansible.git
local host