# aws-ms-eks-reference
Intraedge Managed Services EKS Reference Stack

## About
This is a reference implementation of AWS EKS Stack using [AWS QuickStart templates](https://github.com/aws-quickstart). These templates adds following additional features on top of AWS QuickStart
- Ability to configure [AWS ALB Ingress Controller](https://docs.aws.amazon.com/eks/latest/userguide/alb-ingress.html)

## Getting Started
- Copy the [cloudformation](./cloudformation) template files into a S3 bucket.
- Deploy stack:  [cloudformation/eks-app-stack.yaml](cloudformation/eks-app-stack.yaml) using aws cli or using aws console.


## Limitations
- ~~IAM Service Role for ALB does not include a check for authenticating subject and needs to be manually added post creation of stack~~ **FIXED**: IAM role now includes proper StringEquals conditions for OIDC authentication
- Consider using AWS Load Balancer Controller add-on for EKS instead of manual deployment for easier management

## Security

### Security Best Practices
This reference implementation includes several security features and recommendations:

- **Updated Kubernetes Version**: Uses Kubernetes 1.28 with latest security patches
- **Modern Load Balancer Controller**: Uses AWS Load Balancer Controller v2.6.2 instead of deprecated ALB Ingress Controller
- **Secure IAM Roles**: IAM roles include proper StringEquals conditions for OIDC authentication
- **Encrypted Storage**: RDS instances use storage encryption by default
- **Network Security**: Proper VPC configuration with private/public subnet separation
- **Latest Runtime**: Lambda functions use Python 3.11 runtime

### Security Updates
- PostgreSQL updated to version 15.4 (latest supported)
- Container insights uses pinned versions instead of 'latest' tag
- All deprecated components replaced with current alternatives

### Regular Security Maintenance
1. **Monitor AWS Security Bulletins**: Subscribe to AWS security notifications
2. **Update Dependencies**: Regularly update CloudFormation templates to use latest AMIs and service versions
3. **Review IAM Policies**: Periodically review and minimize IAM permissions
4. **Security Scanning**: Use tools like `cfn-nag` to scan CloudFormation templates for security issues
5. **Network Security**: Regularly review security group rules and VPC configurations

### Recommended Security Tools
- **CloudFormation Linting**: Use `cfn-lint` and `cfn-nag` for template validation
- **Container Scanning**: Use ECR image scanning for container vulnerabilities
- **Runtime Security**: Enable GuardDuty and Security Hub for runtime monitoring
- **Automated Security Checks**: See `.github/workflows/security-checks.yml` for CI/CD integration
- **Security Checklist**: Review `.security-checklist.md` for ongoing security maintenance

## Support
For support around this stack or need help around your AWS Infrastructure and application, contact: [cloudsales@intraedge.com](mailto:cloudsales@intraedge.com)

## References
- [AWS Quick Start EKS](https://github.com/aws-quickstart/quickstart-amazon-eks)
- [AWS ALB Ingress Controller](https://docs.aws.amazon.com/eks/latest/userguide/alb-ingress.html)
- [AWS EKS Monitoring](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/Container-Insights-setup-EKS-quickstart.html)
