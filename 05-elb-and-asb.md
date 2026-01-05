# Elastic Load Balancer and Auto Scaling Groups

## High availability, scaling and elasticity

- Vertical Scaling
  - Increase size of instance
    - Moving from t2.micro to t2.large
  - Common for non-distributed systems (databases)
  - There's usually a limit to how much you can vertically scale 
    - Hardware 

- Horizontal Scaling
  - Increasing number of instances
  - Implies distributed systems
  - Easy to horizontally scale

- High Availability
  - Running app in at least 2 availability zones
  - Survive data center loss

- Scalability vs Elasticity
  - Scalabitiy
    - Scale up (Vertical)
    - Scale out (Horizontal)
  - Elasticity
    - Scaling based on load
  - Agility
    - Ability to make resources availabile

## Elastic Load Balancing

- Multi AZ
- Spread load across multpile downstream instances
- Only exposes a single point of access
- Handles downstream failures
- Does regular health checks on instances
- Provide SSL (HTTPS) termination for websites
- High availability
- Elastic Load Balancer is a managed load balancer
  - AWS guarantees it will be working
  - AWS manages updates, etc
- May cost cost more than your own load balancer, but will be less effort to support and maintain
- **4 Kinds of Load Balancers on AWS**
  - Application load balancer (HTTP/HTTPS only) - Layer 7
  - Network Load Balancer (High performance - allows for TCP) - Layer 7
  - Gateway Load Balancer - Layer 3
  - Classic Load Balancer (retired in 2023) - Layer 4 and 7

## Auto Scaling Group (ASG)

- Multi AZ
- Scale out EC2 instances to match increased load
- Scale in EC2 instances to match decreased load
- Ensure minimum/maximum machines are running
- Automatically register new instances to load balancer
- Replace unhealthy instances
- Cost savings
- Scaling strategies
  - Manually scaling
  - Dynmaic Scaling
  - Scheduled scaling
    - Scale up/down based on usage patterns
  - Target Tracking scaling
    - ASG CPU should stay around 40%
  - Simple/Step scaling
    - CPU greater than 80%
    - CPU lower than 30%
- Predictive Scaling
  - Uses machine learning to predict traffic based on usage patterns

