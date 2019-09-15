1. Use the following command to connect to an azure account

```az login```

2. If you have more than one subscriptions, make sure that you have set the correct one

```az account list```

3. Set the preferred subscription (if more than one)

```az account set --subscription my-subscription-name```

4. Create an azure resource group - a logical group in which azure resources are deployed and managed.
A location is required in order to create a resource group. More about azure resource groups here

https://docs.microsoft.com/en-us/cli/azure/group?view=azure-cli-latest

```az group create --name <clusterName> --location northeurope```

You should get an output similar to this one...

`{
   "id": "/subscriptions/<guid>/resourceGroups/<resourceGroupName>",
   "location": "northeurope",
   "managedBy": null,
   "name": "<myResourceGroup>",
   "properties": {
     "provisioningState": "Succeeded"
   },
   "tags": null
 }`
 
 5. The `az aks` command is used to create an AKS cluster. For example:
 
 `az aks create --resource-group -notYourAksCluster --node-count 1 --node-vm-size Standard_DS1_v2 --enable-addons monitoring --generate-ssh-keys --enable-addons http_application_routing`

 You should get back a json with lots of cluster info
 
 6. Connect to the cluster using the public certificate
 
 `az aks get-credentials --resource-group myAKSCluster --name myAKSCluster`
 
 7. You can verify that you connected to the cluster by using the commands
 
 `kubectl get nodes`
 
 `kubect get pods -n kube-system`

**Note:** Remember to bring down your resources (the cluster plus anything else created by azure related to it) if you're not planning to use it :beer: