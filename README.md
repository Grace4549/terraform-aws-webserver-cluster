# terraform-aws-webserver-cluster

A reusable Terraform module for deploying a webserver cluster on AWS with an ALB, ASG, and VPC.

## Usage
```hcl
module "webserver_cluster" {
  source  = "app.terraform.io/your-org/webserver-cluster/aws"
  version = "1.0.0"

  cluster_name  = "prod-cluster"
  instance_type = "t3.micro"
  min_size      = 2
  max_size      = 5
  environment   = "production"
}
```

## Inputs
| Name | Description | Type | Default |
|------|-------------|------|---------|
| cluster_name | Name of the cluster | string | - |
| instance_type | EC2 instance type | string | t3.micro |
| min_size | Minimum ASG size | number | 1 |
| max_size | Maximum ASG size | number | 2 |
| environment | Environment name | string | dev |

## Outputs
| Name | Description |
|------|-------------|
| alb_dns_name | DNS name of the load balancer |
| asg_name | Name of the Auto Scaling Group |
| vpc_id | ID of the VPC |
