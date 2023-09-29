Containers
==========

# Deploying to Azure Container Apps
- remember to check target port in Ingress and make sure it matches what is exposed. Azure does not always tell you this

## Mounting an Azure File Share to an Azure Container App
https://learn.microsoft.com/en-us/azure/container-apps/storage-mounts-azure-files?tabs=bash#create-the-storage-mount

```powershell
az containerapp env storage set --name [ACA Managed Environment Name] --resource-group [Resource Group] --storage-name [try to make this consistent with the folder mounted] --azure-file-account-name [Azure Storage Account with file share name] --azure-file-account-key [get this from the file share in the Portal] --azure-file-share-name [file share name] --access-mode ReadWrite
```

```powershell
az containerapp show -n [ACA name] -g [resource group] -o yaml > app.yaml
```

```powershell
nano app.yaml
```

```powershell
az containerapp update --name [ACA name] --resource-group [resource group] --yaml app.yaml
```

### mountPath
Example `volumeMounts`:
```yaml
volumeMounts:
- mountPath: /app/name
  volumeName: name
```
- In my experience making the `mountPath` final dir name and the `volumeName` the same makes things a lot simpler.
- In my case, it made the most sense to mount to `app`, but it is worth trying mounting in `mnt`.