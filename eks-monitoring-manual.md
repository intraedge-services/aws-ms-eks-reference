### Monitoring of Kubernetes
  Here we will see how to get container metrics logs and metrics centralized into Cloudwatch(Manual).
#### Verify Prerequisites:
  Before you install Container Insights on Amazon EKS or Kubernetes, verify the [Prerequisites](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/Container-Insights-prerequisites.html)
#### Quick Start Setup for Container Insights on Amazon EKS:
  To complete the setup of Container Insights, you can follow the quick start instructions in this section.
  To deploy Container Insights using the quick start, enter the following command.
```
curl https://raw.githubusercontent.com/aws-samples/amazon-cloudwatch-container-insights/latest/k8s-deployment-manifest-templates/deployment-mode/daemonset/container-insights-monitoring/quickstart/cwagent-fluentd-quickstart.yaml | sed "s/{{cluster_name}}/cluster-name/;s/{{region_name}}/cluster-region/" | kubectl apply -f -
```

Here, we need to give Amazon eks cluster-name and cluster-region according to created infrastructure.

After this, you need to goto the cloudwatch and click on Overview and select container insights.
In drop down you can see the monitoring options like, EKS Pods, EKS Nodes, EKS Cluster, EKS NameSpaces, etc.

#### Deleting Container Insights:
  To delete the container-insights run following command:
```
curl https://raw.githubusercontent.com/aws-samples/amazon-cloudwatch-container-insights/latest/k8s-deployment-manifest-templates/deployment-mode/daemonset/container-insights-monitoring/quickstart/cwagent-fluentd-quickstart.yaml | sed "s/{{cluster_name}}/cluster-name/;s/{{region_name}}/cluster-region/" | kubectl delete -f -
```

#### Reference:
[Quick Start Setup for Container Insights on Amazon EKS](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/Container-Insights-setup-EKS-quickstart.html)
