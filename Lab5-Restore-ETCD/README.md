# OpenShift ETCD Restore Workshop

Welcome to the OpenShift ETCD Restore Workshop! In this workshop, you will learn how to perform an ETCD restore for OpenShift clusters. This process is critical for disaster recovery scenarios and ensuring the stability and availability of your cluster.

### Prerequisites

Before proceeding with the workshop, make sure you have completed the following steps:

1. Log in to the bastion server using your provided credentials.

2. Confirm the health of your OpenShift cluster by running the following command:
```bash
oc get co
```
Ensure that all ClusterOperators are in the "Available" state before proceeding.

3. get the installation kubeconfig file as the active configuration by running the following command:
```bash
export KUBECONFIG=~/ocp-install/auth/kubeconfig
```
This will allow you to interact with your cluster using the correct configuration.

4. Create an ETCD Backup
 Follow the instructions in the [OpenShift Documentation](https://docs.openshift.com/container-platform/4.12/backup_and_restore/control_plane_backup_and_restore/backing-up-etcd.html) to create a backup of your ETCD data. Ensure that you have a valid backup file in your desired location, for example:
```bash
bastion-server# ssh -i ~/ssh-key core@<Master-Node-IP>

sh-4.4# sudo su
sh-4.4# /usr/local/bin/cluster-backup.sh /home/core/backup
sh-4.4# ls -l /home/core/backup
total 93660
-rw-------. 1 root root 95821856 Jul 20 08:53 snapshot_2023-07-20_085308.db
-rw-------. 1 root root    78165 Jul 20 08:53 static_kuberesources_2023-07-20_085308.tar.gz
```

### Workshop Steps

During this workshop, you will be performing an ETCD restore on your OpenShift cluster. The procedures you need to follow will depend on your cluster version. In our scenario, we are using OpenShift Container Platform version 4.12. Therefore, please refer to the official Red Hat documentation specific to your version:

[Restoring Cluster State - Disaster Recovery Scenario](https://docs.openshift.com/container-platform/4.12/backup_and_restore/control_plane_backup_and_restore/disaster_recovery/scenario-2-restoring-cluster-state.html )

Follow the instructions in the documentation carefully to ensure a successful ETCD restore process.

Enjoy the workshop and happy learning!


