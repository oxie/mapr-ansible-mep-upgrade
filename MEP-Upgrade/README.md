
## **Mapr Ecosystem Upgrade - Upgrade**

> Start Playbook

`ansible-playbook -i hosts/upgrade-hosts.yml upgrade.yml -v -b --ask-su-pass`

----------

#### **Preparation Playbook Roles**
- name: MEP-UPGRADE UPGRADE PREPARATION
  hosts: upgrade-hosts
  roles:
     - preparation
     - drill-upgrade
     - hbase-upgrade
     - hive-upgrade
     - httpfs-upgrade
     - spark-upgrade
     - hue-upgrade
     - oozie-upgrade
     - kafka-upgrade

> Spark must be before hue because its dependancy

<br><br>
***!@/#/hosts/upgrade-hosts.yml***
[upgrade-hosts]
 - adress ansible_ssh_user={user} ansible_become_method=su ansible_connection=ssh
 


