Created by Michael Petrinovic 2018

Sample Ansible playbooks from my various Cisco Live Presentations and others.

Be sure to update the inventory.sample file to include the relevant hosts in your environment. Furthermore, update the relevant username and password combinations


NOTE:
If Ansible playbooks fail for the following:

```YAML
# ansible-playbook -i inventory nxos_plays.yml -v --tags "ping" --extra-vars "extra_host=10.66.88.1"
```

This is likely because the container/host hasn't SSH'd into the devices previously, therefore has NOT saved the SSH Fingerprint key

After logging into each system, the Ansible playbook should work correctly

To fix it, you can make the following changes - if you choose:
https://stackoverflow.com/questions/32297456/how-to-ignore-ansible-ssh-authenticity-checking


Sample usage:

Nexus:

```YAML
# ansible-playbook -i inventory nxos_plays.yml --list-tasks

# ansible-playbook -i inventory nxos_plays.yml -v --tags "ping" --extra-vars "extra_host=10.66.88.1"
```

Check on the Nexus 7000/3000/5000

```YAML
# ansible-playbook -i inventory nxos_plays.yml -v --tags "vlan_range" ### Default state is 'present' so will ensure existance of the vlan_range

# ansible-playbook -i inventory nxos_plays.yml -v --tags "vlan_range" --extra-vars "state=absent"   ### State absent will delete the vlan_range
```

ACI

```YAML
# ansible-playbook -i inventory aci_plays.yml --list-tasks
```

Default, will go to Fabric 3 (from my Inventory file), looking for my Cisco Live Tenant
```YAML
# ansible-playbook -i inventory aci_plays.yml -v --tags "query_epgs"
```

Deploy APP
```YAML
# ansible-playbook -i inventory aci_plays.yml -v --tags "deploy_app" --extra-vars "group=aci_sim"
```

DELETE APP
```YAML
# ansible-playbook -i inventory aci_plays.yml -v --tags "deploy_app" --extra-vars "group=aci_sim" --extra-vars "state=absent"
```

WARNING:

These scripts are meant for educational/proof of concept purposes only - as demonstrated at Cisco Live and/or my other presentations. Any use of these scripts and tools is at your own risk. There is no guarantee that they have been through thorough testing in a comparable environment and I am not responsible for any damage or data loss incurred as a result of their use
