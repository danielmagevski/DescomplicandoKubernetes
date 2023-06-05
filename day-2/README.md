# Descomplicando o Kubernetes - Expert Mode

## DAY-2

### O que iremos ver hoje?

Durante a aula de hoje, iremos ver todos os detalhes importantes sobre o menor objeto do Kubernetes, o Pod.
Vamos ver desde a criação de um simples Pod, passando por Pod com multicontainers, com volumes e ainda com limitação ao consumo de recursos, como CPU ou memória.
E claro, vamos aprender como ver todos os detalhes de um Pod em execução e brincar bastante com nossos arquivos YAML.

## Comandos utilizados

<p>kubectl run giropops --image=nginx --port=80</p>
<p>kubectl get pods</p>
<p>kubectl get pods --all-namespaces</p>
<p>kubectl get pods -A</p>
<p>kubectl get pods -n <namespace></p>
<p>kubectl get pods -n kube-system</p>
<p>kubectl get pods <nome-do-pod> -o yaml</p>
<p>kubectl get pods giropops -o yaml</p>
<p>kubectl get pods <nome-do-pod> -o json</p>
<p>kubectl get pods giropops -o json</p>
<p>kubectl get pods <nome-do-pod> -o wide</p>
<p>kubectl get pods giropops -o wide</p>
<p>kubectl describe pods giropops</p>
<p>kubectl delete pods giropops</p>
<p>kubectl logs giropops</p>
<p>kubectl logs -f giropops</p>
<p>kubectl attach giropops -c strigus</p>
<p>kubectl exec giropops -c strigus -it -- sh</p>
<p>kubectl exec giropops -c strigus -- ls</p>
<p>kubectl exec -it ubuntu -- bash</p>

