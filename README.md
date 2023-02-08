## Deploying Terraform EKS Infrastructure

### Prerequisites
- A basic understanding of Terraform
- An AWS account
- Terraform installed on your local machine

### Components created for this Infrastructure
Following components are configured in this example and all relevant resiurces will be created after executing this code:
- EKS Cluster (module "terraform-aws-modules/eks/aws" is used)
- VPC (module "terraform-aws-modules/vpc/aws" is used)

## Steps
1. Clone the repository and open its root directory.
2. Configure your `<YOUR_AWS_ACCESS_KEY>` and `<YOUR_AWS_SECRET_KEY>` with your AWS access key and secret key.
3. Run `terraform init` to initialize Terraform.
4. Run `terraform plan` to see the infrastructure that will be created.
5. If the plan looks good, run `terraform apply` to deploy the infrastructure.
6. Wait for the infrastructure to be created, which may take a few minutes.
7. Once the infrastructure is created, run `terraform output` to see the outputs

## Clean Up
To remove the infrastructure, run `terraform destroy`.

## Basic Commands for Terraform

### Initialize project in directory

    terraform init

### Preview terraform actions

    terraform plan

### Apply configuration with variables

    terraform apply -var-file terraform-dev.tfvars

### Destroy a single resource

    terraform destroy -target aws_vpc.myapp-vpc

### Destroy everything from .tf files

    terraform destroy

### Show resources and components from current state

    terraform state list

### Show current state of a specific resource/data

    terraform state show aws_vpc.myapp-vpc    

### Set avail_zone as custom tf environment variable - before apply

    export TF_VAR_avail_zone="eu-west-3a"
    
### Set AWS configuration through env variables

    export AWS_ACCESS_KEY_ID="anaccesskey"
    export AWS_SECRET_ACCESS_KEY="asecretkey"
    export AWS_DEFAULT_REGION="us-west-2"

### For debugging in TF
    
    export TF_LOG=TRACE   