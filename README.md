# kubernetes In Aws
Kuvernetes Notes

A. Installing Kubernetes

 1. Download Latest version of K8s
     curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
     
 2.Download checksum 
     curl -LO "https://dl.k8s.io/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256"
     
 3. Validate the key
     echo "$(cat kubectl.sha256)  kubectl" | sha256sum --check
     
 4. If validated start installing using the below given command
     sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
     
    If you do not have root access you can still install using
     chmod +x kubectl
     mkdir -p ~/.local/bin
    mv ./kubectl ~/.local/bin/kubectl
    
     
5. Install docker using the given link
      https://docs.docker.com/engine/install/ubuntu/
     
     
6. Start minikube node using
    minikube start --driver=docker
   
7. Check status of node
    minikube status 
      
8. Check ip address of node
   minikube status
   
9. Connecto to minikube node using
    minikube ssh (for local host it works on my pc you can use ssh docker@<ip> and the password : tcuser if given command does not work)
 
