# devops-libraries-and-frameworks



                                      GitOps-ArgoCD Framework

GitOps:
GitOps is an operational framework that takes DevOps best practices used for application development such as version control, collaboration, compliance, and CI/CD tooling, and applies them to infrastructure automation.

ArgoCD:
Argo CD is a declarative, GitOps continuous delivery tool for Kubernetes.
Application definitions, configurations, and environments should be declarative and version controlled. Application deployment and lifecycle management should be automated, auditable, and easy to understand. Refer the below mentioned link to for ArgoCD:
https://argo-cd.readthedocs.io/en/stable/operator-manual/declarative-setup/
Below is the sample Base folder structure of GitOps Strategy:


 ![argoCapture](/uploads/dd31b2bc187631c5dd87a6fb7055fa0b/argoCapture.PNG)

1.	environments:
The environments represents the different development platforms like Dev, QA, Prod. In each environments, we have two different folders: 1. Cluster 2. Apps
First trace to the below path:
1.1 environments>dev>cluster>ArgoCD:

a)	App of Apps:
An app can be created that can creates other apps, which in turn can create other apps. This allows one to declaratively manage a group of apps that can be deployed and configured in concert. Refer the below mentioned link for app-of-apps: 
https://argo-cd.readthedocs.io/en/stable/operator-manual/cluster-bootstrapping/

b)	Apps:
All the services/applications which are needed to be deployed on to the cluster done through apps of that service.  

1.2	 Environments>dev>apps
Here, we create the folder according to the microservices we have in our environment and in the  folder, need to create the kustomization.yaml file. Kustomization is the build recognised by kubectl command. Below is the sample base structure:


 
![kuzCapture](/uploads/b060eba75a8b63d25d48784be35eb5d8/kuzCapture.PNG)




2.	base>apps
Here, we can create the folders according to the microservices available and in the particular application folder, deployment.yaml, service.yaml and kustomization.yaml are to be kept. Ex: guestbook is a microservice. 
3.	 bootstrap>ArgoCD
This is the path to keep all the read documents.
4.	scripts
All the code/scripts file like terraform files etc can be keep in this folder.


