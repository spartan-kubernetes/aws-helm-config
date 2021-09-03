# aws-helm-config
AWS Helm Charts Configs


## AWS Load Balancer Controller

Install the AWS Load Balancer Controller:
1. Follow this guide: https://github.com/aws/eks-charts/tree/master/stable/aws-load-balancer-controller
2. Since the above guide use default values, for each project we must use the `` alb-ingress-controller-chart.yaml`` in the helm upgrade command.
3. ``helm upgrade -i aws-load-balancer-controller eks/aws-load-balancer-controller -n kube-system -f alb-ingress-controller-chart.yaml``

## AWS EFS CSI Driver

Install the EFS CSI Driver:
1. Follow this guide: https://github.com/kubernetes-sigs/aws-efs-csi-driver#installation
2. Since the above guide use default values, for each project we must use the `` efs-storage-controller-chart.yaml`` in the helm upgrade command.
3. To Create the StorageClass within the cluster use: `` efs-storageclass.yaml``
4. ``helm upgrade --install aws-efs-csi-driver --namespace kube-system aws-efs-csi-driver/aws-efs-csi-driver -f efs-storage-controller-chart.yaml``