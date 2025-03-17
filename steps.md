1. Create Cluster \
   Create `dev-cluster`: \
    `Console -> Amazon Elastic Container Service -> Clusters -> (Create Cluster) -> Fargate`
   Check: \
   `aws ecs describe-clusters --clusters dev-cluster --query "clusters[0]"`
   ```
      "serviceConnectDefaults": {
      "namespace": "arn:aws:servicediscovery:us-east-1:692859948557:namespace/ns-2jaqolcd35dt3dfh"
      :...skipping...
      {
      "clusterArn": "arn:aws:ecs:us-east-1:692859948557:cluster/dev-cluster",
      "clusterName": "dev-cluster",
      "status": "ACTIVE",
      "registeredContainerInstancesCount": 0,
      "runningTasksCount": 1,
      "pendingTasksCount": 0,
      "activeServicesCount": 1,
      "statistics": [],
      "tags": [],
      "settings": [],
      "capacityProviders": [
      "FARGATE",
      "FARGATE_SPOT"
      ],
      "defaultCapacityProviderStrategy": [],
      "serviceConnectDefaults": {
      "namespace": "arn:aws:servicediscovery:us-east-1:692859948557:namespace/ns-2jaqolcd35dt3dfh"
      }
      }
   ```
2. Create Task `dev` \
    `Console -> ... Create Task -> `
    - use docker.io/hello-world
    - set port mapping to 8000
    - configure security group to allow inbound traffic to port 8000 \
    - [json definition](taskDefinition.json)
3. Start Service `ecs-service-dev`
    
   `Console ... Create Service -> ` \
   - Assign task and cluster to service \
   - [json definition](serviceDefinition.json)
