# Descomplicando o Kubernetes - Expert Mode

## DAY-17

### O que iremos ver hoje?

Hoje vamos dedicar o nosso tempo para entender o mundo das Network Policies no Kubernetes. Essa é uma ferramenta essencial para a segurança e o gerenciamento eficaz da comunicação entre os Pods em um cluster Kubernetes. Vamos aprender como as Network Policies funcionam, suas aplicações práticas e como você pode implementá-las para proteger suas aplicações no Kubernetes. Com certeza será um dia com muito conteúdo e aprendizado

## Comandos utilizados

<p>eksctl create cluster -f eksctl.yaml</p>
<p>kubectl api-versions | grep networking</p>
<p>kubectl get nodes</p>
<p>eksctl create addon --name vpc-cni --version v1.16.0-eksbuild.1 --cluster eks-cluster --force</p>
<p>eksctl get addon --cluster eks-cluster</p>
<p>"enableNetworkPolicy": "true"</p>
<p>kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.9.5/deploy/static/provider/cloud/deploy.yaml</p>
<p>kubectl get pods -n ingress-nginx</p>
<p>kubectl wait --namespace ingress-nginx \</p>
<p>--for=condition=ready pod \</p>
<p>--selector=app.kubernetes.io/component=controller \</p>
<p>--timeout=90s</p>
<p>kubectl create ns giropops</p>
<p>kubectl apply -f giropops-deployment.yaml -n giropops</p>
<p>kubectl apply -f giropops-service.yaml -n giropops</p>
<p>kubectl apply -f redis-deployment.yaml -n giropops</p>
<p>kubectl apply -f redis-service.yaml -n giropops</p>
<p>kubectl apply -f giropops-ingress.yaml -n giropops</p>
<p>kubectl run -ti alpine --image alpine -- sh</p>
<p>apk add curl</p>
<p>kubectl apply -f permitir-redis-somente-mesmo-ns.yaml -n giropops</p>
<p>kubectl run -it --rm --image redis redis-client -- redis-cli -h redis-service.giropops.svc.cluster.local ping</p>
<p>kubectl run -it --rm -n giropops --image redis redis-client -- redis-cli -h redis-service.giropops.svc.cluster.local ping</p>
<p>kubectl apply -f nao-permitir-nada-externo.yaml -n giropops</p>
<p>kubectl run -it --rm --image redis redis-client -- redis-cli -h redis-service.giropops.svc.cluster.local ping</p>
<p>kubectl run -it --rm --image curlimages/curl curl-client -- curl giropops-senhas.giropops.svc</p>
<p>kubectl run -it --rm -n giropops --image curlimages/curl curl-client -- curl giropops-senhas.giropops.svc</p>
<p>kubectl apply -f permitir-ingress-controller.yaml -n giropops</p>
<p>kubectl run -it --rm --image curlimages/curl curl-client -- curl giropops-senhas.giropops.svc</p>
<p>kubectl apply -f deny-all-ingress.yaml -n giropops</p>
<p>kubectl apply -f permitir-somente-ingress-entre-app-redis-mesmo-ns.yaml -n giropops</p>
<p>kubectl get networkpolicies -n giropops</p>


