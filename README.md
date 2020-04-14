# poorspray

# move all vars to one area
# create a download role
# do not show skipped tasks
# sriov ipam - how is that provisioned?

Supports only single master coniguration

1. Make sure you can ssh to any host from the master as root with no passwd
2. Run poorspray on the master node
3. git clone: https://github.com/shahar-klein/poorspray.git
4. Set your inventory according to inventory/basic/hosts.Example
5. Go over all the vars in inventory/basic/group_vars/k8s-cluster/k8s-cluster.yaml and make sure this is what you want
6. Run poorspray on the master node
Deploy:
*Run reset before any deploy always: ansible-playbook -i inventory/basic/hosts reset.yaml*
Deploy: ansible-playbook -i inventory/basic/hosts cluster.yaml


Tips:
Some variables can be set from the command line. For example:
 # ansible-playbook -i inventory/basic/hosts.sjc3 cluster.yaml --extra-vars '{"cluster_default_route":'10.0.0.1'}'


