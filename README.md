# devops-eks-terraform-github-actions
project deployment through terraform

devops-eks-terraform-github-actions/
├── microservices/
│   └── app1/
│       ├── app.py
│       ├── requirements.txt
│       └── Dockerfile
├── terraform/
│   ├── providers.tf
│   ├── variables.tf
│   ├── main.tf
│   ├── vpc.tf
│   ├── eks.tf
│   ├── iam.tf
│   └── outputs.tf
├── k8s-manifests/
│   ├── namespace.yaml
│   ├── deployment.yaml
│   └── service.yaml
├── .github/
│   └── workflows/
│       └── cicd.yaml
└── README.md

