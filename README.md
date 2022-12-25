# Helm-installation
# Installation guide for helm
Agenda :- Installing and configuring helm for personal development.

Pre-requisite:-
> Ubuntu 20.04 LTS OS with 4 gb ram 

Steps:-
1) Docker installation
sudo apt update
sudo apt install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
apt-cache policy docker-ce
sudo apt install docker-ce
sudo systemctl status docker
sudo usermod -aG docker ${USER}
docker --version


2) Minikube installation
sudo apt update
sudo apt install apt-transport-https
sudo apt upgrade
[ -f /var/run/reboot-required ] && sudo reboot -f
sudo apt install virtualbox virtualbox-ext-pack
wget https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
chmod +x minikube-linux-amd64
sudo mv minikube-linux-amd64 /usr/local/bin/minikube
minikube version

3) Kubectl installation
curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl
chmod +x ./kubectl
sudo mv ./kubectl /usr/local/bin/kubectl
kubectl version -o json  --client

4) Basic minikube and kubectl configuration

minikube start
kubectl cluster-info
kubectl get nodes
minikube ip
vi /etc/hosts
ip app.minikube.local

5) Helm installation

wget https://get.helm.sh/helm-v3.9.3-linux-amd64.tar.gz
tar xvf helm-v3.9.3-linux-amd64.tar.gz
sudo mv linux-amd64/helm /usr/local/bin
rm helm-v3.4.1-linux-amd64.tar.gz
rm -rf linux-amd64
helm version

6) Helm initialization

helm repo add stable https://charts.helm.sh/stable
helm search repo stable
helm install stable mysql

-------------------------------------------------------------------------
Please like and share this video
this installation document is available at below git link

Bye! 

Note:-
To resolve vt-x is not available (verr_vmx_no_vmx) in ubuntu issue.

sudo apt-get install cpu-checker
sudo kvm-ok 
reboot the vm

