# Executing this playbook locally

## Install Ansible and other required packages
1. [Install Ansible](http://docs.ansible.com/ansible/intro_installation.html)
Linux instalaltion command: *yum -y install ansible*.

1. [Install python](http://boto.cloudhackers.com/en/latest/getting_started.html)
Linux instalaltion command: *yum -y install python*.

1. [Install boto3](https://boto3.readthedocs.io/en/latest/guide/quickstart.html#installation)
Linux instalaltion command: *pip install boto3*.

1. [Install boto](http://boto.cloudhackers.com/en/latest/getting_started.html)
Linux instalaltion command: *pip install boto*.



## Fill up samplegroupvars.yml with necessary variables.
- *vi samplegroupvars.yml*


## Create group_vars folder.
- *mkdir group_vars*


## Move samplegroupvars.yml to group_vars and rename it to "all".
- *mv samplegroupvars.yml group_vars/all*


## Define your AWS Access key.
- *export AWS_ACCESS_KEY="your access key here"*


## Define your AWS Secret key.
- *export AWS_SECRET_TOKEN="your secret key here"*


## Run ansible playbook.
- *ansible-playbook provision_instance.yml --connection=local -i hosts -u ec2-user --extra-vars " aws_access_key=${AWS_ACCESS_KEY} aws_secret_token=${AWS_SECRET_TOKEN}"*
