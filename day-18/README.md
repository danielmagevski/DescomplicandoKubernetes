# Descomplicando o Kubernetes - Expert Mode

## DAY-18

### O que iremos ver hoje?

Hoje, conheceremos profundamente o mundo do RBAC (Role-Based Access Control) no Kubernetes. O RBAC é um mecanismo essencial que permite a administradores de sistemas definirem regras de acesso específicas para usuários e serviços dentro de um cluster Kubernetes. Você aprenderá sobre a importância do RBAC para a segurança e a gestão eficaz dos recursos de um cluster, incluindo como criar e gerenciar usuários, atribuir papéis e permissões específicas, e configurar acessos baseados em funções para diferentes tipos de usuários e serviços. Vamos explorar exemplos práticos de como aplicar o RBAC para controlar o acesso a recursos do cluster, como pods, deployments e serviços, garantindo que apenas usuários autorizados possam executar operações específicas. Ao final deste guia, você terá um entendimento sólido sobre como implementar e gerenciar o controle de acesso baseado em funções no Kubernetes, proporcionando um ambiente de cluster mais seguro e eficiente.

## Comandos utilizados

<p>openssl genrsa -out developer.key 2048</p>
<p>openssl req -new -key developer.key -out developer.csr -subj "/CN=developer"</p>
<p>cat developer.csr | base64 | tr -d '\n'</p>
<p>kubectl apply -f developer.yaml</p>
<p>kubectl get csr</p>
<p>kubectl describe csr developer</p>
<p>kubectl certificate approve developer</p>
<p>kubectl get csr developer -o jsonpath='{.status.certificate}' | base64 --decode > developer.crt</p>
<p>kubectl api-resources</p>
<p>kubectl api-resources | grep pods</p>
<p>kubectl api-resources --namespaced=false</p>
<p>kubectl api-resources -o wide</p>
<p>kubectl create ns dev</p>
<p>kubectl apply -f developer-role.yaml</p>
<p>kubectl get roles -n dev</p>
<p>kubectl describe role developer -n dev</p>
<p>kubectl apply -f developer-rolebinding.yaml</p>
<p>kubectl get rolebindings -n dev</p>
<p>kubectl describe rolebinding DeveloperRoleBinding -n dev</p>
<p>kubectl config set-credentials developer --client-certificate=developer.crt --client-key=developer.key --embed-certs=true</p>
<p>kubectl config set-context developer --cluster=kubernetes --namespace=dev --user=developer</p>
<p>kubeclt config get-contexts</p>
<p>kubectl config use-context developer</p>
<p>kubectl get deployments</p>
<p>kubectl run nginx --image=nginx -n dev</p>
<p>openssl genrsa -out platform.key 2048</p>
<p>openssl req -new -key platform.key -out platform.csr -subj "/CN=platform/O=platform"</p>
<p>cat platform.csr | base64 | tr -d '\n'</p>
<p>kubectl apply -f platform-csr.yaml</p>
<p>kubectl get csr</p>
<p>kubectl certificate approve platform</p>
<p>kubectl get csr platform -o jsonpath='{.status.certificate}' | base64 --decode > platform.crt</p>
<p>kubectl apply -f platform-clusterrole.yaml</p>
<p>kubectl apply -f platform-clusterrolebinding.yaml</p>
<p>kubectl config set-credentials platform --client-certificate=platform.crt --client-key=platform.key --embed-certs=true</p>
<p>kubectl config set-context platform --cluster=NOME-DO-CLUSTER --user=platform</p>
<p>kubectl config use-context platform</p>
<p>kubectl get pods --all-namespaces</p>
<p>kubectl get clusterrolebindings</p>
<p>kubectl get clusterroles</p>
<p>kubectl apply -f service-account.yaml</p>
<p>kubectl get serviceaccounts service-account-example -o yaml</p>
<p>kubectl apply -f service-account-secret.yaml</p>
<p>kubectl get secrets service-account-example-token -o yaml</p>
<p>kubectl get secret service-account-example-token -o jsonpath='{.data.token}' | base64 --decode</p>
<p>kubectl apply -f service-account-role.yaml</p>
<p>kubectl apply -f service-account-rolebinding.yaml</p>
<p>kubectl get roles</p>
<p>kubectl get rolebindings</p>
<p>kubectl apply -f pod-service-account.yaml</p>
<p>kubectl exec -it pod-service-account -- ls /var/run/secrets/kubernetes.io/serviceaccount</p>
<p>kubectl exec -it pod-service-account -- cat /var/run/secrets/kubernetes.io/serviceaccount/token</p>
<p>kubectl exec -it pod-service-account -- sh</p>
<p>curl -k -H "Authorization: Bearer $(cat /var/run/secrets/kubernetes.io/serviceaccount/token)" https://kubernetes.default.svc/api/v1/namespaces/default/pods</p>
<p>curl -k -H "Authorization: Bearer $(cat /var/run/secrets/kubernetes.io/serviceaccount/token)" https://kubernetes.default.svc/api/v1/namespaces/default/services</p>
<p>kubectl delete serviceaccount service-account-role</p>
<p>kubectl delete secret service-account-example-token</p>
<p>kubectl delete rolebinding service-account-rolebinding</p>
