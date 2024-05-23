# Descomplicando o Kubernetes - Expert Mode

## DAY-15

### O que iremos ver hoje?

Hoje, exploraremos as funcionalidades e aplicações do Kyverno, uma ferramenta de gerenciamento de políticas essencial para a segurança e eficiência de clusters Kubernetes. Com uma abordagem detalhada e prática, você aprenderá a usar o Kyverno para automatizar tarefas cruciais, garantir a conformidade com normas e regras estabelecidas e melhorar a administração geral de seus ambientes Kubernetes.

## Comandos utilizados

<p>helm repo add kyverno https://kyverno.github.io/kyverno/</p>
<p>helm repo update</p>
<p>helm install kyverno kyverno/kyverno --namespace kyverno --create-namespace</p>
<p>kubectl get pods -n kyverno</p>
<p>kubectl get crd | grep kyverno</p>
<p>kubectl apply -f require-resources-limits.yaml</p>
<p>kubectl apply -f pod.yaml</p>
<p>https://playground.kyverno.io/</p>
<p>kubectl apply -f add-label-namespace.yaml</p>
<p>kubectl create ns giropops</p>
<p>k get all -n kyverno</p>
