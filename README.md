# Cluster management

## Prepare nodes

Copy the SSH key to the servers. Make sure `sshpass`` is installed. The script `copy-ssh-key-to-servers` can be used.

## Setup kubernetes

1. Run `ansible-playbook -i inventory.yml playbook/site.yml --private-key=../ssh-key/id_rsa` to bootstrap the cluster.
2. Pick the master node label it appropriately to make the ingress only accessible `kubectl label node master svccontroller.k3s.cattle.io/enablelb=true`.
3. Deploy all manifests from the `kubernetes` folder.
4. Deploy the dashboards in grafana