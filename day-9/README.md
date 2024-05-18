# Descomplicando o Kubernetes - Expert Mode

## DAY-9

### O que iremos ver hoje?

O que é o Ingress?

O Ingress é um recurso do Kubernetes que gerencia o acesso externo aos serviços dentro de um cluster. Ele funciona como uma camada de roteamento HTTP/HTTPS, permitindo a definição de regras para direcionar o tráfego externo para diferentes serviços back-end. O Ingress é implementado através de um controlador de Ingress, que pode ser alimentado por várias soluções, como NGINX, Traefik ou Istio, para citar alguns.

Tecnicamente, o Ingress atua como uma abstração de regras de roteamento de alto nível que são interpretadas e aplicadas pelo controlador de Ingress. Ele permite recursos avançados como balanceamento de carga, SSL/TLS, redirecionamento, reescrita de URL, entre outros.


## Comandos utilizados

<p>kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.9.5/deploy/static/provider/aws/deploy.yaml</p>
<p>kubectl apply -f app-deployment.yaml</p>
<p>kubectl apply -f app-service.yaml</p>
<p>kubectl apply -f redis-deployment.yaml</p>
<p>kubectl apply -f redis-service.yaml</p>
<p>kubectl get pods</p>
<p>kubectl get services</p>
<p>kubectl apply -f ingress.yaml</p>
<p>kubectl describe ingress ingress-1</p>
<p>kubectl port-forward services/giropops-senhas 5000:5000</p>
<p>kubectl get ingress ingress-1 -o jsonpath='{.status.loadBalancer.ingress[0].hostname}'</p>
<p>kubectl get ingress ingress-1 -o jsonpath='{.status.loadBalancer.ingress[0].ip}'</p>
<p>curl ENDEREÇO_DO_INGRESS/giropops-senhas</p>
<p>eksctl create cluster --name=eks-cluster --version=1.25 --region=us-east-1 --nodegroup-name=eks-cluster-nodegroup --node-type=t3.medium --nodes=2 --nodes-min=1 --nodes-max=2 --managed</p>
<p>eksctl delete cluster --name=eks-cluster</p>
<p>kubectl config current-context</p>
<p>kubectl config use-context kind</p>

