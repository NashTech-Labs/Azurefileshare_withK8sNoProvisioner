# Using "No-Provisioner" in Kubernetes with Azure File Share

This template provides a set of YAML files to help you configure and use the "no-provisioner" feature in Kubernetes with Azure File Share.

## Steps to Use:

1. **Prepare Azure File Share:**
   - Create a Storage Account in Azure.
   - Generate a shared access key.
   - Create a file share within the storage account.

2. **Update Configuration Files:**
   - Open `azure-fileshare-pv.yaml` and replace `<YOUR_STORAGE_SIZE>` and `<YOUR_SHARE_NAME>` with your desired storage size and Azure File Share name.
   - Open `azure-fileshare-pvc.yaml` and replace `<YOUR_REQUESTED_STORAGE>` with the size you want for your PersistentVolumeClaim.

3. **Apply Configurations:**
   - Apply the configurations using the following commands:
     ```bash
     kubectl apply -f azure-fileshare-pv.yaml
     kubectl apply -f azure-fileshare-sc.yaml
     kubectl apply -f azure-fileshare-pvc.yaml
     ```

4. **Verify:**
   - Verify that the PV, StorageClass, and PVC are created successfully:
     ```bash
     kubectl get pv,pvc
     ```

Now, you have a PersistentVolume (PV) connected to your Azure File Share using the "no-provisioner" feature in Kubernetes. The PersistentVolumeClaim (PVC) is ready to be used by your applications.

Feel free to customize the configurations according to your specific needs.
