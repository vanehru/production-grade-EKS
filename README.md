# production-grade-EKS

1. Networking (VPC, Subnets, Routes)

aws_vpc
aws_subnet (public/private)
aws_route_table, aws_internet_gateway, aws_nat_gateway 


2. IAM Roles

IAM roles for:
EKS cluster
Worker nodes
ServiceAccount for ESO, HPA


3. EKS Setup

Use terraform-aws-eks module (by AWS)
module "eks" {
  source  = "terraform-aws-modules/eks/aws"
  cluster_name = "your-cluster"
  ...
}

 
4. ALB Ingress Controller (AWS Load Balancer Controller)

Add required IAM roles + helm chart
Create Ingress resources in Kubernetes for routing traffic



5. CloudFront + S3 (Static SPA or sorry page)

aws_cloudfront_distribution
aws_s3_bucket


6. Route53 + ACM

aws_acm_certificate (us-east-1 for CloudFront)
aws_route53_zone, aws_route53_record


7. AWS WAF

aws_wafv2_web_acl linked to CloudFront or ALB


8. Karpenter

Separate helm chart + Provisioner CRD
IAM role with karpenter.sh/discovery tag


9. ElastiCache & Aurora MySQL

aws_elasticache_cluster (or replication group)
aws_rds_cluster (Aurora MySQL)
Ensure they are in private subnets + correct SGs


10. ECR + SSM Parameter Store

aws_ecr_repository
aws_ssm_parameter
