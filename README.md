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
 5. To check the installed version is up to date or not
     kubectl version --client
