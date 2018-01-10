# Kubernetes Setup


### Kubernetes Setup Information
+ Kubernetes should be really able to run anywhere
+ But, There are more integrations for certain Cloud providers like AWS & GCE (Google cloud )
+ Things like Volumes and External Load Balances work only with supported Cloud providers.
+ If Integration for your Cloud platforms is not aviliable, Then you can still use Kubernetes, But you will not be able to use Volumes and External Load Balances. 
+ First we will use a minikube to quickly spin up a local single machine with a Kubernetes cluster
+ Then we will spin up a cluster on AWS using kops 
+ Kops is a tool can be used to spin up highly aviliable production cluster

### Other useful Information

+ Using AWS Free tier (gives you 750 hrs/mo of t2.micro)
  - http://aws.amazon.com
+ Using Local machine
  - Use minikube from https://github.com/kubernetes/minikube
