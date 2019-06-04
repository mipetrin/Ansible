Sample Ansible Playbooks from various presentations that I do at Cisco Live and other events, including Customer Presentations/Demos, DevNet, DevNet Express Events, Internal Training that I feel the demo should be shared, etc:

* Cisco Live Melbourne 2018: BRKDCN-2602
* Cisco Live Orlando 2018: BRKDCN-2011
* Cisco Live Barcelona 2019: BRKDCN-2011
* Cisco Live Melbourne 2019: BRKDCN-2602
* Cisco Live San Diego 2019: BRKDCN-2011

> Within each sub-directory, is the script and an additional README. It will be documented in that README what each script is expected to achieve and how to use that particular script.

> Be sure to update the inventory.sample file to include the relevant hosts in your environment. Furthermore, update the relevant username and password combinations

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




Created by Michael Petrinovic 2018


WARNING:

These scripts are meant for educational/proof of concept purposes only - as demonstrated at Cisco Live and/or my other presentations. Any use of these scripts and tools is at your own risk. There is no guarantee that they have been through thorough testing in a comparable environment and I am not responsible for any damage or data loss incurred as a result of their use
