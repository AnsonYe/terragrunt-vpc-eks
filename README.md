# Terragrunt VPC EKS

## Infrastructure Live V1

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

### Development Environment

The `dev` directory contains the Terraform code for the infrastructure required in the development environment. To see more details or to make changes to this environment, navigate to `dev/vpc`.

### Staging Environment

The `staging` directory contains the Terraform code for the infrastructure required in the staging environment. For more details or to make changes to this environment, navigate to `staging/vpc`.

### Getting Started

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

## Infrastructure Modules - VPC

This repository contains the `vpc` module inside the `infrastructure-modules` directory, which defines the resources necessary to create a Virtual Private Cloud (VPC) in AWS. This module can be reused across different environments such as `dev`, `staging` etc.

The structure of the repository is as follows:

```
.
└── vpc
    ├── 0-versions.tf
    ├── 1-vpc.tf
    ├── 2-igw.tf
    ├── 3-subnets.tf
    ├── 4-nat.tf
    ├── 5-routes.tf
    ├── 6-outputs.tf
    ├── 7-variables.tf
    └── README.md
```


### VPC Module

The `vpc` module within the `infrastructure-modules` directory is a reusable piece of Terraform code that allows consistent and streamlined creation of a VPC in AWS. By using this module, we can ensure consistency across different environments by simply adjusting the variables, rather than rewriting resource code.

To use this module in your environment, your Terraform code should include a `module` block as shown below:

```hcl
module "vpc" {
  source = "../infrastructure-modules/vpc"
  // Any required variables here
}
```
Remember to replace ../infrastructure-modules/vpc with the correct relative path to the vpc module directory, and define any required variables within the module block.

### Contributing

Changes to the infrastructure should go through a pull request process where they can be reviewed before being applied. Please make sure any changes are well-documented and include updates to this `README.md` if necessary.
