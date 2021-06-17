
# Tutoriel K8S sur Microsoft Azure Kubernetes Services (MS AKS)

Se connecter sur AKS

    az login

Creer un groupe de ressources

    az group create \
        --name MyResourceGroup \
        --location francecentral

Créer un cluster (la version gratuite est limitée à 2 noeuds)

    az aks create \
      -g MyResourceGroup \
      -n MyManagedCluster \
      --generate-ssh-keys --node-count 2

Attendre 3-5 minutes... que les nodes soient créés

Se connecter au cluster (pour .kube/config)

    az aks get-credentials \
        --resource-group MyResourceGroup \
        --name MyManagedCluster

Vérifier que les nodes sont prets

    kubectl get nodes

## Précautions d'emploi

### Load Balancers

* https://docs.microsoft.com/fr-fr/azure/aks/load-balancer-standard

### Pour un exemple complet

* https://itnext.io/running-your-microservices-securely-on-aks-417a110b2e76?sk=40002aac0f7d5af48fc781c844cfb9ba
* https://medium.com/microsoftazure/secure-your-microservices-on-aks-part-2-5496bf2ba00c
* https://medium.com/microsoftazure/secure-your-microservices-on-aks-part-3-the-network-dfde7d26af8c

