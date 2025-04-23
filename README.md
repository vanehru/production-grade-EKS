# production-grade-EKS


terraform/
│
├── modules/
│   ├── vpc/
│   ├── eks/
│   ├── rds/
│   ├── redis/
│   ├── cloudfront/
│   ├── alb/
│   ├── waf/
│   ├── route53/
│   └── karpenter/
│
├── environments/
│   ├── dev/
│   └── prod/
│
└── main.tf / variables.tf / outputs.tf
