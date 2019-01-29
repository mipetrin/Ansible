Created by Michael Petrinovic 2018

Sample Ansible playbooks for Cisco Live Melbourne 2018: BRKDCN-2602

Be sure to update the inventory.sample file to include the relevant hosts in your environment. Furthermore, update the relevant username and password combinations


Sample usage:

Nexus:
# ansible-playbook -i inventory nxos_plays.yml --list-tasks

# ansible-playbook -i inventory nxos_plays.yml -v --tags "ping" --extra-vars "extra_host=10.66.88.1"

Check on the Nexus 7000/3000/5000
# ansible-playbook -i inventory nxos_plays.yml -v --tags "vlan_range" ### Default state is 'present' so will ensure existance
# ansible-playbook -i inventory nxos_plays.yml -v --tags "vlan_range" --extra-vars "state=absent"   ### State absent will delete


ACI

# ansible-playbook -i inventory aci_plays.yml --list-tasks

Default, will go to Fabric 3, looking for my Cisco Live Tenant
# ansible-playbook -i inventory aci_plays.yml -v --tags "query_epgs"

Deploy APP
# ansible-playbook -i inventory aci_plays.yml -v --tags "deploy_app" --extra-vars "group=aci_sim"

DELETE APP
# ansible-playbook -i inventory aci_plays.yml -v --tags "deploy_app" --extra-vars "group=aci_sim" --extra-vars "state=absent"
