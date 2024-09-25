Install Minikube on an Ubuntu Linux machine.
1.Install Kubectl (Kubernetes Command Line Tool)
kubectl is the command-line tool used to interact with Kubernetes clusters
# Update the package index and install the required packages
sudo apt-get update
sudo apt-get install -y apt-transport-https ca-certificates curlkubectl get nodes
![Screenshot (11)](https://github.com/user-attachments/assets/2a4c1bdf-41f8-44f9-879a-f5fd15b5c92d)



# Download and add Google's GPG key
sudo curl -fsSLo /usr/share/keyrings/kubernetes-archive-keyring.gpg https://packages.cloud.google.com/apt/doc/apt-key.gpg

# Add the Kubernetes apt repository
echo "deb [signed-by=/usr/share/keyrings/kubernetes-archive-keyring.gpg] https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee /etc/apt/sources.list.d/kubernetes.list

# Update the package index again
sudo apt-get update

# Install kubectl
sudo apt-get install -y kubectl


Here’s how you can install Minikube on an Ubuntu Linux machine:

1. Install Prerequisites
Before installing Minikube, you need to make sure your system has the required dependencies.

a) Install Kubectl (Kubernetes Command Line Tool)
kubectl is the command-line tool used to interact with Kubernetes clusters. To install it, run:

bash
Copy code
# Update the package index and install the required packages
sudo apt-get update
sudo apt-get install -y apt-transport-https ca-certificates curl

# Download and add Google's GPG key
sudo curl -fsSLo /usr/share/keyrings/kubernetes-archive-keyring.gpg https://packages.cloud.google.com/apt/doc/apt-key.gpg

# Add the Kubernetes apt repository
echo "deb [signed-by=/usr/share/keyrings/kubernetes-archive-keyring.gpg] https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee /etc/apt/sources.list.d/kubernetes.list

# Update the package index again
sudo apt-get update

# Install kubectl
sudo apt-get install -y kubectl


b) Install Virtualization Tool (Hypervisor)
sudo apt-get install -y virtualbox virtualbox-ext-pack

You can also use Docker as the driver for Minikube. Ensure Docker is installed:
sudo apt-get install -y docker.io

Make sure Docker is running:
sudo systemctl start docker
sudo systemctl enable docker

Install Minikube:
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube
minikube version

Start Minikube:
Using VirtualBox as a driver:
minikube start --driver=virtualbox
minikube start --driver=docker

