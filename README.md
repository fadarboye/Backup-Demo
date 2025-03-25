<a href="https://www.linkedin.com/in/adeboye-famurewa-700b9426/"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white"></a> 

![](https://img.shields.io/badge/Follow%20%ad-1.4k-blue?logo=linkedin&style=social "Follow in/Adeboye on LinkedIn") 


![Screenshot 2025-03-25 021635](https://github.com/user-attachments/assets/f06aa678-8b8e-46d2-8cff-cdfc1e355da9)


# AKS BACK-UP IN AZURE

This is a quick guides focus on a command-line experience to easily and quickly run all the required steps. for backing up your AKS cluster in Azure.


### PREREQUISITES

1. Before installing Backup Extension in the AKS cluster, ensure that the `CSI drivers` and `Snapshots` are Enabled for your cluster. If disabled, please enable them.


2. Azure Backup for AKS supports clusters using either a `system-assigned managed identity` or a `user-assigned managed identity` for backup operations. It does not service principal.


3. The Backup Extension during installation fetches Container Images stored in Microsoft Container Registry (MCR). If you enable a `firewall` on the AKS cluster, the extension installation process might fail due to access issues on the Registry.  Allow MCR access from the firewall.


4. For cluster using a Private Virtual Network and Firewall, apply the FQDN/application rules


5. If you have any previous installation of `Velero` in the AKS cluster, you need to delete it before installing Backup Extension.


6. If you are using Azure policies in your AKS cluster, ensure that the extension namespace `dataprotection-microsoft` is excluded from these policies to allow backup and restore operations to run successfully.


7. Finally, If you are using Azure network security group (NSG) to filter network traffic between Azure resources in an Azure virtual network then set an `inbound rule` to allow service tags `azurebackup` and `azurecloud`.

