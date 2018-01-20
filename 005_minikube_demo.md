# Minikube Demo

### Set up a Local Kuberneties using Minikube

##### Install the required packages  i.e VirtualBox, Kubectl and Minikube and follow the below steps

+ Open Windows powershell


		PS C:\Users\asm\Desktop\Kuberneties> ls

        		Directory: C:\Users\asm\Desktop\Kuberneties

	  	Mode                LastWriteTime     Length Name
	  	----                -------------     ------ ----
	  	-a---         1/20/2018   8:38 AM   52721152 kubectl.exe
	  	-a---         1/20/2018   8:39 AM   41454592 minikube.exe
    
+ Commands to check minikube version


		PS C:\Users\asm\Desktop\Kuberneties> .\minikube.exe version
		minikube version: v0.24.0
		
+ Starting a minikube local cluster

		PS C:\Users\asm\Desktop\Kuberneties> .\minikube.exe start
		There is a newer version of minikube available (v0.24.1).  Download it here:
		https://github.com/kubernetes/minikube/releases/tag/v0.24.1

		To disable this notification, run the following:
		minikube config set WantUpdateNotification false
		Starting local Kubernetes v1.8.0 cluster...
		Starting VM...
		Downloading Minikube ISO
		 139.09 MB / 139.09 MB [============================================] 100.00% 0s
		Getting VM IP address...
		Moving files into cluster...
		Downloading localkube binary
		 148.25 MB / 148.25 MB [============================================] 100.00% 0s
		Setting up certs...
		Connecting to cluster...
		Setting up kubeconfig...
		Starting cluster components...
		Kubectl is now configured to use the cluster.
		Loading cached images from config file.
		PS C:\Users\asm\Desktop\Kuberneties>
		
		
+ From the above logs we can see that our local minikube cluster has started and minikube will generate a config file with cluster details

		PS C:\Users\asm\Desktop\Kuberneties> ls C:\Users\asm\.kube\config


		    Directory: C:\Users\asm\.kube


		Mode                LastWriteTime     Length Name
		----                -------------     ------ ----
		-a---         1/20/2018   8:45 AM        446 config


		PS C:\Users\asm\Desktop\Kuberneties> cat C:\Users\asm\.kube\config
		apiVersion: v1
		clusters:
		- cluster:
		    certificate-authority: C:\Users\asm\.minikube\ca.crt
		    server: https://192.168.99.100:8443
		  name: minikube
		contexts:
		- context:
		    cluster: minikube
		    user: minikube
		  name: minikube
		current-context: minikube
		kind: Config
		preferences: {}
		users:
		- name: minikube
		  user:
		    as-user-extra: {}
		    client-certificate: C:\Users\asm\.minikube\client.crt
		    client-key: C:\Users\asm\.minikube\client.key
		PS C:\Users\asm\Desktop\Kuberneties>
		
+ Now Run a pirticular image on cluster

		PS C:\Users\asm\Desktop\Kuberneties> .\kubectl.exe run hello-minikube --image=gcr.io/google_containers/echoserver:1.4 --
		port=8080
		deployment "hello-minikube" created
		
+ From the above logs we can see that the image deployment has done successfully 

+ The following are few more useful commans

		PS C:\Users\asm\Desktop\Kuberneties> .\kubectl.exe expose deployment hello-minikube --type=NodePort
		service "hello-minikube" exposed
		PS C:\Users\asm\Desktop\Kuberneties>


		PS C:\Users\asm\Desktop\Kuberneties> .\kubectl.exe get svc
		NAME             TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)          AGE
		hello-minikube   NodePort    10.107.141.240   <none>        8080:30713/TCP   1m
		kubernetes       ClusterIP   10.96.0.1        <none>        443/TCP          33m
		PS C:\Users\asm\Desktop\Kuberneties>

		PS C:\Users\asm\Desktop\Kuberneties> .\minikube.exe service hello-minikube --url
		http://192.168.99.100:30713


		PS C:\Users\asm\Desktop\Kuberneties> .\kubectl.exe get pods
		NAME                              READY     STATUS    RESTARTS   AGE
		hello-minikube-57889c865c-nrclq   1/1       Running   0          7m


+ To stop the local minikube cluster run the following command.

		PS C:\Users\asm\Desktop\Kuberneties> .\minikube.exe stop
		Stopping local Kubernetes cluster...
		Machine stopped.

