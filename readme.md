# Deploying Kubernetes on-premise in Azure Arc (Fully Automated)

There are 3 scripts to perform fully automated deployment of kubernetes cluster into Azure Arc:
1. Deploy Kubernetes master node and X nuber of worker ndoes, please use this script [setup-k8sfull.sh](https://github.com/bramyeni/bash-scripts/blob/main/setup-k8sfull.sh )
2. Deploy Storage class using this script [setup-sc.sh](https://github.com/bramyeni/bash-scripts/blob/main/setup-sc.sh) from the following storage:
   - smb (connect to smb server, install samba package, configure smb.conf, create mountpoint, start samba server, create storage class csi-smb)
   - nfs (connect to nfs server, install nfs-server package, create /etc/exports for mountpoint, start nfs-server, create storage class csi-nfs)
   - azuresmb (create storage account, create premium file server with smb protocol, create share smbmount, get the key, create secret, create storage class csi-smb)
   - azurenfs (create storage account, create premium file server with nfs protocol, create share nfsmount, create service endpoint on specified vnet's subnet, create storage class csi-nfs)
3. Deploy Azure Arc which connect to Kubernetes clusetr and storage class above (still creating it :-) )
