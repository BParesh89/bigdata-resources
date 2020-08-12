## Kubernetes

### Pods

    $ kubectl get pods ## get list of all pods in current namespace
    $ kubectl get pods --all-namespaces ## get list of all pods in all namespaces
    $ kubectl describe pod monkey ## desribe the state of pod money
    
    
### apply
    # Create a service using the definition in example-service.yaml.
    kubectl apply -f example-service.yaml

    # Create a replication controller using the definition in example-controller.yaml.
    kubectl apply -f example-controller.yaml

    # Create the objects that are defined in any .yaml, .yml, or .json file within the <directory> directory.
    kubectl apply -f <directory>

### create Deployments
Create single deployment

    $ kubectl run monkey --image=monkey --record

### Scaling PODs

    $ kubectl scale deployment/POD_NAME --replicas=N
    
### Secrets

    $ kubectl get secrets
    $ kubectl create secret generic --help
    $ kubectl create secret generic mysql --from-literal=password=root
    $ kubectl get secrets mysql -o yaml
    
