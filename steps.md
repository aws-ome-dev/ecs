1. Create Cluster

    `Console -> Amazon Elastic Container Service -> Clusters -> (Create Cluster) -> Fargate`
2. Create Task
    `... Create Task -> `
    - use docker.io/hello-world
    - set port mapping to 8000
    - configure security group to allow inbound traffic to port 8000
3. Start Service
    
   `... Create Service -> `
   Assign task and cluster to service
