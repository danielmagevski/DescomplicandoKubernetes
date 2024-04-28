# Descomplicando o Kubernetes - Expert Mode

## DAY-3

### O que iremos ver hoje?

Durante o dia de hoje nós iremos aprender sobre um objeto muito importante no Kubernetes, o Deployment. Nós iremos ver todos os detalhes para que possamos ter uma visão completa sobre o que é um Deployment e como ele funciona. Agora que já sabemos tudo sobre como criar um Pod, acho que já podemos colocar um pouco mais de complexidade no nosso cenário, não é mesmo? Bora lá!  

## Comandos utilizados

<p>kubectl apply -f deployment.yaml</p>
<p>kubectl get pods -l nginx-deployment</p>
<p>kubectl get replicasets -l app=nginx</p>
<p>kubectl describe deployment nginx-deployment</p>
<p>kubectl rollout status deployment nginx-deployment</p>
<p>kubectl get pods -l app=nginx-deployment -o yaml</p>
<p>kubectl rollout undo deployment nginx-deployment --to-revision=1</p>
<p>kubectl rollout pause deployment nginx-deployment</p>
<p>kubectl rollout resume deployment nginx-deployment</p>
<p>kubectl rollout status deployment nginx-deployment</p>
<p>kubectl rollout history deployment nginx-deployment</p>
<p>kubectl rollout history deployment nginx-deployment --revision=1</p>
<p>kubectl delete deployment nginx-deployment</p>






