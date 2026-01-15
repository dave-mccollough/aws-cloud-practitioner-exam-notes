# Other Compute Services

## Docker

- Software platform to deploy apps
- Apps are packaged in containers
- You can run several containers on one server - resources are shared with the host OS
- Apps run the same regardless of where they are run
  - Any machine
  - Precdicatble behavior
  - Easier to maintain and deploy
- Containers can be scaled up/down quickly

- Docker images are stored in Docker Repositories
  - [Public Docker Hub](https://hub.docker.com)
    - Find base images for different technologies or operating systems
- Amazon provides a private container registry
  - Amazon ECR (Elastic Container Registry)

## ECS, Fargate, and ECR

- **ECS(Elastic Container Service)**
  - Run Docker containers on AWS
  - You must provision and maintain the infrastructure (EC2 instances)
  - AWS manages starting/stoping containers
  - Has integrations with Application Load Balancer\

- **Fargate**
  - Launch Docker containers on AWS
  - Do not need to manage underlying infrastructure
  - Serverless offering
  - AWS runs containers based on CPU/RAM you need

- **ECR(Elastic Container Registry)**
  - Private Docker registry on AWS
  - This is wher you can store your Docker images

## EKS (Elastic Kubernetes Service)

- Run managed Kubernetes on AWS
- Containers can be hosted on
  - EC2 Instances
  - Fargate

## Serverless

- New paradigm where code is deployed and cloud provider manages the infrastructure
- FaaS - Functions as a Service

## Lambda

- Functions as a Service
- Scaling is automated
- Pay per request and compute time
- Integrates with AWS services
- Event Driven - Functions are invoked when needed
- Works with many programming languages
- Monitoring through AWS CloudWatch
- Easy to get more resources per function
  - Increasing RAM will improve CPU and network

## Amazon API Gateway

- Fully managed service to create, publish, maintain and monitor secure APIs
- Serverless scalable
- Supports RESTful and WebSocket APIs
- Supports security, user authentication, API throttling, APIK keys, monitoring

## AWS Batch

- Fully managed batch processing - any scale
- Batch will dynamically launch EC2 or EC2 Spot Instances
- Provides the right amount of compute/memory
- Batch jobs are defined as Docker images and run on EC2
- No time limit
- Relys on EBS/instance store for disk space

## Amazon Lightsail

- Virtual servers, storage, databases and networking
- Low and predictable pricing
- Simpler alternative to using EC2, RDS, ELB, EBS, Route 53
- Can configure monitoring and notifications 
- Use cases
  - Simple web applications
  - Websites
  - Dev/Test environment
  - High availability but no autoscaling

