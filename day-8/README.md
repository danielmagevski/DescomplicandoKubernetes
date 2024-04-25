# Descomplicando o Kubernetes - Expert Mode

## DAY-8

### O que iremos ver hoje?

Hoje é dia de falar sobre duas coisas super importantes no mundo do Kubernetes, hoje nós vamos falar sobre *Secrets* e *ConfigMaps*.

Sim, essas duas peças fundamentais para que você possa ter a sua aplicação rodando no Kubernetes da melhor forma possível, pois elas são responsáveis por armazenar as informações sensíveis da sua aplicação, como por exemplo, senhas, tokens, chaves de acesso, configurações, etc.

Depois do dia de hoje você vai entender como funciona o armazenamento de informações sensíveis no Kubernetes e como você pode fazer para que a sua aplicação possa consumir essas informações da melhor forma possível.

## Comandos utilizados

<p>echo -n 'giropops' | base64</p>
<p>echo -n 'Z2lyb3BvcHM=' | base64 -d</p>
<p>kubectl create -f giropops-secret.yaml</p>
<p>kubectl get secret giropops-secret</p>
<p>kubectl get secret giropops-secret -o yaml</p>
<p>kubectl describe secret giropops-secret</p>
<p>kubectl create secret generic giropops-secret --from-literal=username=<SEGREDO> --from-literal=password=giropops</p>
<p>kubectl apply -f giropops-pod.yaml</p>
<p>kubectl get pods</p>
<p>kubectl exec giropops-pod -- env</p>
<p>kubectl apply -f dockerhub-secret.yaml</p>
<p>openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout chave-privada.key -out certificado.crt</p>
<p>kubectl create secret tls meu-servico-web-tls-secret --cert=certificado.crt --key=chave-privada.key</p>
<p>kubectl get secret meu-servico-web-tls-secret -o yaml</p>
<p>kubectl create configmap nginx-config --from-file=nginx.conf</p>
<p>kubectl apply -f nginx-config.yaml</p>
<p>kubectl get configmap nginx-config -o yaml</p>
<p>kubectl apply -f nginx.yaml</p>
<p>kubectl get pods</p>
<p>kubectl expose pod nginx</p>
<p>kubectl get services</p>
<p>kubectl port-forward service/nginx 4443:443</p>
<p>curl -k https://localhost:4443</p>