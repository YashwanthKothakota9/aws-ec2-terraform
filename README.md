# <p style="text-align: center;">Provisioning AWS resources using Terraform</p>

------------------

Terraform is an cloud-agnostic software tool helps to configure and manage Infrastructure as Code (IaC).

This repo has the terraform hashicorp configuration language files which provision AWS resources such as 
- VPC
- Subnet
- EC2 Instance
- Internet Gateway
- Route Table
- Route Table Association
- Security Group


Files:
- [providers.tf](/aws-ec2-terraform/providers.tf): It tells the terraform which cloud provider to use.
- [terraform.tfvars](/aws-ec2-terraform/terraform.tfvars): It contains all the input variables to the terraform. 
- [start-script.sh](/aws-ec2-terraform/start-script.sh): This is the bash file which will be run on EC2 Instance after creating it.
- [main.tf](/aws-ec2-terraform/main.tf): It tells the terraform what are all the resources, integrations between them, security settings on them should be provisioned on cloud.

After `terraform apply` it creates two file to store the state of the resources created `terraform.tfstate` and `terraform.tfstate.backup`.

Outputs can be captured after creating resources and can be stored in `output.json` file. This can be local or can be stored remotely to make available to any `CICD` pipelines to access the resources.

High level view of Terraform:
![HLD](/aws-ec2-terraform/HLD.png)