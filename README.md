# Ansible Jenkins JCasC Job-DSL
Tha base idea is taken from the [Darin Pope's repository](https://github.com/darinpope/ansible-jenkins).\
As a result of the current repository configuration, the Jenkins service infrastructure will be created with the codes and without touching the UI:
- The Ansible playbook in`playbooks/playbook.yml`:
  - Will install the jenkins
  - Install jenkins-plugin-manager
  - Install plugins listed in `playbook/files/plugins.yml`
  - (You can also uncomment the agent play in the playbook to configure an Jenkins agent)
- Jenkins Configuration As Code (JCasC) (`playbook/files/jenkins.yml`)
  - Will configure the base jenkins infrastructure and create a sample job dsl (The default username/password of the jenkins will be `admin:admin`)
- You can also look at the `playbook/files/init.groovy.d/` directory and `playbook/files/override.conf`)
- Do not forget to edit the `inventory/the.hosts` and `./ansible.cfg` files.

#### This configuration has been tested on Ubuntu 22.04 and 20.04.


## Prerequisites
* `ansible-galaxy collection install -r requirements.yml`
 directory.
## Startup
* `ansible-playbook -i playbooks/playbook.yml`

## You can access to the jenkins on port 8080
* Jenkins URL: http://IP:8080