# Infrastructure Live V1

This repository contains the Terraform code to create Virtual Private Clouds (VPC) in AWS for both development (`dev`) and staging (`staging`) environments.

The structure of the repository is as follows:
```
.
├── dev
│   └── vpc
│       ├── 0-provider.tf
│       ├── 1-vpc.tf
│       ├── 2-igw.tf
│       ├── 3-subnets.tf
│       ├── 4-nat.tf
│       ├── 5-routes.tf
│       ├── 6-outputs.tf
│       └── dev
│           └── vpc
│               ├── terraform.tfstate
│               └── terraform.tfstate.backup
└── staging
    └── vpc
        ├── 0-provider.tf
        ├── 1-vpc.tf
        ├── 2-igw.tf
        ├── 3-subnets.tf
        ├── 4-nat.tf
        ├── 5-routes.tf
        └── 6-outputs.tf
```

## Development Environment

The `dev` directory contains the Terraform code for the infrastructure required in the development environment. To see more details or to make changes to this environment, navigate to `dev/vpc`.

## Staging Environment

The `staging` directory contains the Terraform code for the infrastructure required in the staging environment. For more details or to make changes to this environment, navigate to `staging/vpc`.

## Getting Started

Before running any Terraform commands, ensure you have Terraform installed and AWS credentials set up in your environment.

1. **Initialize your Terraform workspace**

    Navigate to the directory of the environment you wish to work on (e.g., `dev/vpc` or `staging/vpc`) and run:

    ```
    terraform init
    ```

2. **Plan your changes**

    Check the changes that will be made to your infrastructure:

    ```
    terraform plan
    ```

3. **Apply your changes**

    Apply the desired changes to your infrastructure:

    ```
    terraform apply
    ```

Please make sure to check the Terraform plan output before applying any changes.

## Contributing

Changes to the infrastructure should go through a pull request process where they can be reviewed before being applied. Please make sure any changes are well-documented and include updates to this `README.md` if necessary.
