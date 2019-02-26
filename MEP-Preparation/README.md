
## **Mapr Ecosystem Upgrade - Preparation**

> Start Playbook

`ansible-playbook -i hosts/preparation-hosts.yml preparation.yml -v -b --ask-su-pass`

----------

#### **Preparation Playbook Roles**
- name: MEP-UPGRADE UPGRADE PREPARATION
  hosts: preparation-hosts
  roles:
     - dependencies
     - drill-preparation
     - hbase-preparation
     - hive-preparation
     - httpfs-preparation
     - hue-preparation
     - oozie-preparation
     - spark-preparation
     - stop-services
     - fetch-backups #
     - start-services

<br><br>
***!@/#/hosts/preparation-hosts.yml***
[preparation-hosts]
 - mapr1-dev.neterra.skrill.net ansible_ssh_user={user} ansible_become_method=su ansible_connection=ssh
 - mapr2-dev.neterra.skrill.net ansible_ssh_user={user} ansible_become_method=su ansible_connection=ssh
 - mapr3-dev.neterra.skrill.net ansible_ssh_user={user} ansible_become_method=su ansible_connection=ssh
 - mapr4-dev.neterra.skrill.net ansible_ssh_user={user} ansible_become_method=su ansible_connection=ssh


