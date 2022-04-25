# Basic Commands
1.  kubectl cluster-info (to know cluster informations)
2.  kubectl get nodes (to get list of nodes running in k8s)
3.  kubectl get namespace ( to get list of group or resources)
4.  kubectl get pods ( to get running pods running in a node)
5.  kubectl get pods --namespace=kube-system ( gives pods availabe in kube-system group)
6.  kubectl run nginx1 --image=nginx ( to run a pod of name nginx from image nginx by default image is fetched from dockerhub )
7.  kubectl describe pod nginx1 ( it gives details about nginx1 pod created in command 6)
8.  kubectl get pods -o wide ( information of pods available more than normal)
9.  kubectl delete pod ngin                                                                                           (Note That U cannot curl the nginx1 pod from outside the cluster i.e from host )
10.  kubectl create deployment nginx-deployment --image nginx ( deployment is used to create pods of same pod and autoscaling can be used using this as well we can create service i.e. nginx server, mysql server etc.)
11.   kubectl get deployments (gives the list of deployed pods)
     (Note that this deployment is wil create a pod with itself and you can further increase number of pods using deployment to know write command k get pods)
12. kubectl get pods ( fetch the pods created by deployment )
13. kubectl describe pod podname (it describes all the information of pod created using deployment )
14. kubectl scale deployment nginx-deployment --replicas=3 (it will create two more replica in total of 3 of the node)
15. kubectl expose nginx-deployment --port=8080 --target-port=80 ( it will expose the deployed pods under nginx-deployment to given port of post)
16. kubectl get services ( gives list of all the running services now you can also see a service named nginx-deployment and it's ip address will be completely different from the pod's ip address a
17. kubectl delete deployment nginx-deployment (it delete the deployment)
18. kubectl delete svc nginx-deployment (delete services start by exposing the nginx-deployment deployment)
19. minikube stop (it stops minikube node)

NOTE: the ip assigned to deployment is known cluster ip address and it can not be accessed outside the cluster to accessed from outside the cluster you have to use load balancer
20. To expose the node outside the cluster use --types while exposing the nods
    (ex. kubectl expose deployment nginx-deployment --type=NodePort --port=3000
    here --port=3000 refers to the port 3000 of the pod that will be exposed to cluster  and by getting    
    services  (kubectl get svc) we get  in PORT(S) column 3000:<any port no>/tcp
     to access this pod get the url using (minikube service nginx-deployment  --url) 
     u will get a url by using this u can access the pods from outside the cluster)
21. minikube dashboard ( to get all the pods status in your web browser)
     
