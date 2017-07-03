# Executing this playbook locally

## Fill up samplegroupvars.yml with necessary variables.
*vi samplegroupvars.yml*


## Move samplegroupvars.yml to group_vars and rename it to "all".
*mv samplegroupvars.yml group_vars/all*

## Define your AWS Access key.
*export AWS_ACCESS_KEY="your access key here"*

## Define your AWS Secret key.
*export AWS_SECRET_TOKEN="your secret key here"*

## Run ansible playbook.
*ansible-playbook provision_instance.yml --connection=local -i hosts -u ec2-user --extra-vars " aws_access_key=${AWS_ACCESS_KEY} aws_secret_token=${AWS_SECRET_TOKEN}"*
