Getting Started with Kubernetes nginx proxy pass to node js:
-----------------------------------------------------------

This k8s application is basically a simple hello world program in node js which will be redirected by nginx proxy.

* Steps for execution:

Building the containers:
-----------------------

         1. Goto <repo>/nginx-proxy-nodejs/containers/node folder 
         2. Build the node image using the below commands:

			   ### $ docker build -t <imagename>:<tag> -f Dockerfile.node .

         3. Goto <repo>/nginx-proxy-nodejs/containers/nginx folder 
         4. Build the nginx image using the below commands:

			   ### $ docker build -t <imagename>:<tag> -f Dockerfile.app .

Execute the kubermetes definitions:
----------------------------------

         1. Goto <repo>/nginx-proxy-nodejs/ directory and execute the below scripts.
         
         
         ### $ kubectl create -f appnode.yaml
         
         2. Verify the pods and deployment and service using the below.
         
         Pods:
         
         ### $ kubectl get pods
         
         Deployments:
         
         ### $ kubectl get deployments
         
         Services:
         
         ### $ kubectl get svc
         
         ### bash-3.2$ kubectl get svc
         ### NAME         TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)        AGE
         ### appnode-s    NodePort    10.106.79.238   <none>        80:32001/TCP   37m
         ### kubernetes   ClusterIP   10.96.0.1       <none>        443/TCP        5d17h


         
Accessing the application:

        ### http://localhost:32001
        

    
   
