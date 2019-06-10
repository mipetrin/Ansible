Sample Ansible Playbooks from various presentations that I do at Cisco Live and other events, including Customer Presentations/Demos, DevNet, DevNet Express Events, Internal Training that I feel the demo should be shared, etc:

> Be sure to update the Inventory to match your environments. Furthermore, feel free to update the variables to be more reflective of what you would like for your environment

Sample usage:

Nexus:
```YAML
# ansible-playbook -i NXOS_Inventory 6a-NXOS.yml
# ansible-playbook -i NXOS_Inventory 6b-NXOS_Ping.yml
# ansible-playbook -i NXOS_Inventory 6c-NXOS_Check_VLANs.yml
```

All others:
```YAML
# ansible-playbook -i CiscoLive_Inventory <playbook_name>
```


Created by Michael Petrinovic 2019


WARNING:

These scripts are meant for educational/proof of concept purposes only - as demonstrated at Cisco Live and/or my other presentations. Any use of these scripts and tools is at your own risk. There is no guarantee that they have been through thorough testing in a comparable environment and I am not responsible for any damage or data loss incurred as a result of their use
