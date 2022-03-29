 Install Docker
$  sudo apt update && apt -y install docker.io

 Install kubectl
$  curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl &&   chmod +x ./kubectl && sudo mv ./kubectl /usr/local/bin/kubectl

 Install Minikube
$  curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 && chmod +x minikube && sudo mv minikube /usr/local/bin/

 Start Minikube
$  apt install conntrack
$  minikube start --vm-driver=none
$  minikube status

To download helm
curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3
chmod 700 get_helm.sh
./get_helm.sh

To verify the installation use the following command
which helm


Let’s create Our First Helm Chart

helm list

helm repo add stable https://charts.helm.sh/stable

helm repo list

helm search repo jenkins   # it will show jenkins chart present in our repo
helm search repo tomcat
helm repo remove stable
helm show values stable/tomcat
helm show chart stable/tomcat
helm show all stable/tomcat
helm create helloworld
tree helloworld


helm install testchart2 stable/tomcat
helm install testchart3 stable/tomcat --version 4.0.0
helm install testchart stable/tomcat --set service.type=NodePort  #testchart = release_name, stable = repo_name, tomcat = chart_name 

helm get all <release_name>  # after install

helm get values <release_name>  # after install

helm get menifest <release_name>  # after install

helm history <release_name>

#upgrade a release
helm upgrade <release_name> <chart_name>

helm rollback <release_name> <revision_name>

helm pull stable/tomcat

helm pull stable/tomcat --untar

helm status <release_name>
helm delete testchart # it will delete all resources releated to testchart

to uninstall helm
which helm ( to see which folder its installed )
rm -rf /usr/local/bin/helm
kubectl get all
