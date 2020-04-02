# aws-ms-eks-reference
Intraedge Managed Services EKS Reference Stack

## About
This is a reference implementation of AWS EKS Stack using [AWS QuickStart templates](https://github.com/aws-quickstart). These templates adds following additional features on top of AWS QuickStart
- Ability to configure [AWS ALB Ingress Controller](https://docs.aws.amazon.com/eks/latest/userguide/alb-ingress.html)

## Getting Started
- Copy the [cloudformation](./cloudformation) template files into a S3 bucket.
- Deploy stack:  [cloudformation/eks-app-stack.yaml](cloudformation/eks-app-stack.yaml) using aws cli or using aws console.


## Limitations
- IAM Service Role for ALB does not include a check for authenticating subject and needs to be manually added post creation of stack See https://docs.aws.amazon.com/eks/latest/userguide/create-service-account-iam-policy-and-role.html#create-service-account-iam-role.  We are working on adding a custom resource so that this manual step can be avoided.

## Support
For support around this stack or need help around your AWS Infrastructure and application, contact: [cloudsales@intraedge.com](mailto:cloudsales@intraedge.com)

## References
- [AWS Quick Start EKS](https://github.com/aws-quickstart/quickstart-amazon-eks)
- [AWS ALB Ingress Controller](https://docs.aws.amazon.com/eks/latest/userguide/alb-ingress.html)


