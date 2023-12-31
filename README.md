# TAP-terraform
Hello! This is my repo for my Terraform config files for the TAP GIG Assessment.

By running this Terraform configuration, this is the infrastructure that will be loaded in the AWS Account:

## Architecture Diagram
![TAP-GIG-Infrastructure Diagram drawio](https://github.com/mukminpitoyo/TAP-terraform/assets/89132892/5812f186-79d5-4024-9e59-a3d56bb3899b)

## Requirements of the Infra
As specified previously, these were the requirements of the web application/infrastructure:
1) The infrastructure must be provisioned on AWS automatically without manual intervention
2) The web application service should still be up when an AWS availability zone fails
3) The web traffic should be load balanced across multiple availability zones
4) Any changes to the infrastructure must be performed without manual intervention
5) The design should be based on best practices with security in mind

## Deck and Video Explanation
Link to Slides: https://docs.google.com/presentation/d/17zuJ6sH2_kKMItTLBuvlGAZF6J7Y9Nw4uQPQVVeJgtc/edit?usp=sharing

Link to the presentation & video demonstration of deployment: https://youtu.be/SsGohLOr138

Link to the deployed Elastic Beanstalk application: http://tap-gig-env.eba-rmxaef7f.ap-southeast-1.elasticbeanstalk.com/  _(PS: This will be taken down soon and won't be up forever, do not want to incur too much cost on my AWS account haha)_

## Assumptions & Constraints
From the instructions given, these were some of the assumptions that I made:
1) "_infrastructure must be provisioned automatically without manual intervention_" -> By this, I assume that **manual intervention** refers to logging in to AWS Management Console UI and launching the AWS Services from there. To tackle this, we use Terraform (Infrastructure as Code) to spin up the required AWS Services instead
2) Since we are migrating the on-premises workload to AWS Cloud, and the engineers need to migrate a Web App running on Windows Server 2019, we kept to the same Windows Server 2019 platform and adopt a simple & straightforward **lift-and-shift model**
3) The style of this infrastructure is kept simple since it is a template that is intended to be used by different engineers to facilitate the migration of on-premise Windows Server 2019 setups
4) Focus of the infrastructure is on High Availability, Performance, and Security. Cost is not assumed to be an important factor in choosing of AWS Service
