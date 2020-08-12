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
    
### Troubleshooting
    $ kubectl describe <podname>   # see described status of pod
    $ kubectl logs <podname>    # see logs of kubernetes pod
    $ kubectl exec -it <podname> /bin/bash  # to enter running pod and get bash terminal to debug/modify running container
    $ kubectl get nodes --show-labels
    $ kubectl get events

### Sample kubernetes yaml

    ---
    apiVersion: v1
    kind: Pod
    metadata:
      name: currency-dimension-job
      labels:
        app: currency-dimension-job
    spec:
      containers:
        - name: '${JOB_NAME}-image'
          image: '${ARTIFACTORY_IMAGE}'
          command:
            - /spark-submit.sh
          args:
            - '--total-executor-cores'
            - '1'
            - '--executor-memory'
            - 4G
            - '--num-executors'
            - '1'
            - '--conf'
            - spark.scheduler.mode=FAIR
            - '--conf'
            - spark.scheduler.allocation.file=fair_scheduler.xml
            - '--conf'
            - spark.sql.shuffle.partitions=5
            - '--class'
            - com.ibm.epm.framework.Controller
            - controller_deploy.jar
            - '-t'
            - CurrencyDimension
            - '-g'
            - '${GOAL}'
          imagePullPolicy: IfNotPresent
          env:
            - name: CLOUDANT_USERNAME
              valueFrom:
                secretKeyRef:
                  name: cloudant-credentials
                  key: cloudant_username
            - name: CLOUDANT_PASSWORD
              valueFrom:
                secretKeyRef:
                  name: cloudant-credentials
                  key: cloudant_password
            - name: CLOUDANT_ACCOUNT
              value: '${CLOUDANT_ACCOUNT}'
            - name: CLOUDANT_DATABASE
              value: '${CLOUDANT_DATABASE}'
            - name: CLOUDANT_DECRYPTION_KEY
              valueFrom:
                secretKeyRef:
                  name: cloudant-decryption-key
                  key: id_rsa
          resources:
            requests:
              cpu: 0.001
              memory: 10Mi
            limits:
              cpu: 2
              memory: 2Gi
          volumeMounts:
            - name: '${NAMESPACE}-volume'
              mountPath: /mnt
      restartPolicy: Never
      imagePullSecrets:
        - name: artifactory-registry-secret
      volumes:
        - name: '${NAMESPACE}-volume'
          persistentVolumeClaim:
            claimName: 'pv-claim-${NAMESPACE}-cos'
    ---
    apiVersion: v1
    kind: Service
    metadata:
      name: currency-dimension-job
    spec:
      clusterIP: None
      selector:
        app: currency-dimension-job
        
Here, arguments like NAMESPACE, CLOUDANT_USERNAME, JOB_NAME etc can be supplied by bash script executing yaml or kubernetes secrets.


## Docker

### Build

Build an image from the Dockerfile in the current directory and tag the image

    docker build -t myimage:1.0 .
List all images that are locally stored with the Docker Engine

    docker image ls
Delete an image from the local image store

    docker image rm alpine:3.4
    
### Share

Pull an image from a registry

    docker pull myimage:1.0
Retag a local image with a new image name and tag

    docker tag myimage:1.0 myrepo/myimage:2.0
Push an image to a registry

    docker push myrepo/myimage:2.0 

### Run

Run a container from the Alpine version 3.9 image, name the running container “web” and expose port 5000 externally,
mapped to port 80 inside the container.

    docker container run --name web -p 5000:80 alpine:3.9
    
Stop a running container through SIGTERM

    docker container stop web
Stop a running container through SIGKILL

    docker container kill web
List the networks

    docker network ls

