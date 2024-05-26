# Learn Terraform Resources
This repo is a companion repo to the [Define Infrastructure with Terraform Resources](https://developer.hashicorp.com/terraform/tutorials/configuration-language/resource) tutorial, containing Terraform configuration files to provision two publicly EC2 instances and an ELB.

## Goals
* Create
  * EC2 instance / runs a PHP web application
  * security group / application -- is made -- publicly accesible

## Prerequisites
* Terraform [v1.2+](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli) installed locally
* AWS account with [associated credentials](https://registry.terraform.io/providers/hashicorp/aws/latest/docs#authentication-and-configuration)
  * via
    * add in the 'provider' block
    * environment variables
      * 'AWS_ACCESS_KEY_ID'
      * 'AWS_SECRET_ACCESS_KEY'
      * 'AWS_REGION'
    * credential files
      * `aws config` & pass the 'AWS_ACCESS_KEY_ID' & 'AWS_SECRET_ACCESS_KEY'

## How to run?
* `terraform init`
* `terraform apply`
  * Open in your desired browser 'application-url' to check you can access to the application deployed
* `terraform destroy`
  * clean up all the infrastructure

## Notes
* 'init-script.sh'
  * allows
    * installing dependencies
    * starting a sample PHP application
* [random_pet](https://registry.terraform.io/providers/hashicorp/random/latest/docs/resources/pet)
  * NO required arguments
* [aws_instance](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/instance)
* [security group](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-security-groups.html)
  * allows
    * ingress traffic on a port
  * [resource configuration](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group)