# Descomplicando o Kubernetes - Expert Mode

## DAY-5

### O que iremos ver hoje?

Hoje nós iremos falar como instalar o Kubernetes em um cluster com 03 nodes, onde um deles será o control plane e os outros dois serão os workers.

Nós iremos utilizar o kubeadm para configurar o nosso cluster. Nós iremos conhecer no detalhe como criar um cluster utilizando 03 instancias EC2 da AWS, mas você pode utilizar qualquer outro tipo de instância, desde que seja uma instância Linux, o importante é entender o processo de instalação do Kubernetes e como seus componentes trabalham juntos.


## Comandos utilizados

<p>sudo swapoff -a</p>

```bash
cat <<EOF | sudo tee /etc/modules-load.d/k8s.conf
overlay
br_netfilter
EOF
```

```bash
sudo modprobe br_netfilter</p>
sudo modprobe overlay</p>
cat <<EOF | sudo tee /etc/sysctl.d/k8s.conf</p>
net.bridge.bridge-nf-call-iptables  = 1
net.bridge.bridge-nf-call-ip6tables = 1
net.ipv4.ip_forward                 = 1
EOF
```

<p>sudo sysctl --system</p>
<p>sudo apt-get update && sudo apt-get install -y apt-transport-https curl gpg</p>
<p>curl -fsSL https://pkgs.k8s.io/core:/stable:/v1.28/deb/Release.key | sudo gpg --dearmor -o /etc/apt/keyrings/kubernetes-apt-keyring.gpg</p>
<p>echo 'deb [signed-by=/etc/apt/keyrings/kubernetes-apt-keyring.gpg] https://pkgs.k8s.io/core:/stable:/v1.28/deb/ /' | sudo tee /etc/apt/sources.list.d/kubernetes.list</p>
<p>sudo apt-get update</p>
<p>sudo apt-get install -y kubelet kubeadm kubectl</p>
<p>sudo apt-mark hold kubelet kubeadm kubectl</p>
<p>sudo apt-get update && sudo apt-get install -y apt-transport-https ca-certificates curl gnupg lsb-release</p>
<p>curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg</p>
<p>echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null</p>
<p>sudo apt-get update && sudo apt-get install -y containerd.io</p>
<p>sudo containerd config default | sudo tee /etc/containerd/config.toml</p>
<p>sudo sed -i 's/SystemdCgroup = false/SystemdCgroup = true/g' /etc/containerd/config.toml</p>
<p>sudo systemctl enable --now kubelet</p>
<p>sudo systemctl status containerd</p>
<p>sudo systemctl restart containerd</p>
<p>sudo kubeadm init --pod-network-cidr=10.10.0.0/16 --apiserver-advertise-address=172.31.61.217</p>
<p>kubectl config view</p>
<p>sudo kubeadm token create --print-join-command</p>
<p>kubectl apply -f https://github.com/weaveworks/weave/releases/download/v2.8.1/weave-daemonset-k8s.yaml</p>
<p>kubectl get pods -n kube-system</p>
<p>kubectl get nodes</p>
<p>kubectl create deployment nginx --image=nginx --replicas 3</p>
<p>kubectl get pods</p>
<p>kubectl get pods -o wide</p>
<p>kubectl describe node controlplane</p>
<p>kubectl describe node worker</p>



