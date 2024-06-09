Deployed 3-Tier Architecture E-commerce Application on to a Kubernetes cluster which is AWS EKS (Three Tier Architecture Deployment  of E-Commerce on to Application on AWS EKS.

This project consists of 6 micro services, 2 Data Bases and 1 in memory Datastore.
About Project: -
This project is called a Stan’s Robot-Shop is a sample microservice application. basically it is demo E-commerce project are selling robots and some artificial intelligence products and this project is actually written by IBM Folks for they have a product called instana to demo their project which is a application performance monitoring tool they use this demo project.  
Tools and Technologies Used: -
GitHub, Kubernetes, Docker, EKS Cluster, EC2 instance, minikube, kubectl, eksctl, Nginx, ingress, ALB-Controller.

Implementation:-
1.Pre-requsites: -EC2- instance of t2.xlarge for windows system AWSCLI To Be configured, Docker Minikube, KubeCTL, EKSCTL.  

2. So I have forked the repository and made some changes with help of mentor so that it can easily deployable.

3. Instead of deploying them individually as docker container what I have done is in the EKS folder I have created helm chart for it.

4. Configure IAM OIDC provider by exporting cluster name. 

5.configure AWS console with respect to region and after that check IAM OIDC provider is configure or not if not configure it.

6.Now I proceeded with ALB-configuration is because I want expose to this Robot-shop Application with external world for that I had exposed it using ingress and ingress controller only for the web-application that is hosted in nginx I was create ingress along with deployment and service.

7.for that first I created IAM Policy to create and deploy ALB-Controller (i.e., ALB ingress controller).   

8. for that i downloaded IAM policy and created a service account for ALB-controller with Kube-system name space.

9.After that I added helm chart for the ALB-controller and I installed ALB-controller.

10.sometimes my cloud formation basically ALB-controller and service account whenever im trying create there are some errors in case of service account I have noticed the cloud formation fails and so then I went to that particular cloud formation stack i deleted and recreated it.

11. now added the helm chart and proceeded with installing the helm.

12. now I created EKS-cluster with ec2 instances without fargate because fargate will not support redis component and persistent volumes also not support.

13.helm chart created the ALB-CONTROLLER make sure the ALB-controller pods are up and running.

14. now created and configured ebs-csi-driver(plugin) by creating eksctl, iam-service account and add it as add-on.

15.now deployed the project as helm chart by creating namespace as robot-shop.

16.check the pods status is running or not.

17.expose the application to external world by Load-Balancer type service or ingress for the service apply the ingress.yaml now it created ingress and now you go to load balancer sometimes it is provisioning state wait for some time when state is active my application is deployed it is up & running.

18. now you can register for the first time and next time by login and check the robot’s details and pricing.

