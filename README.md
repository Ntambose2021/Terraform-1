# Terraform-1
EC2 Script

terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 3.0" # Optional but recommended in production
    }
  }
}

# Provider Block
provider "aws" {
  profile = "default" # AWS Credentials Profile configured on your local desktop terminal  $HOME/.aws/credentials
  region  = "us-east-1"
}

# Resource Block

resource "aws_instance" "ec2demo" {
  ami           = "ami-04505e74c0741db8d"
  
  # Amazon Linux in us-east-1, update as per your region
  instance_type = var.practice1


  tags = {
    Name = "myec2"
  }
}
