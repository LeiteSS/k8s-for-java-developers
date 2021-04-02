# Rodando sua aplicação Java no Kubernetes

- Tive problema ao digitar os comandos: `minikube -p dev.to ssh` e `minikube image load java-k8s`, o comando que está no `Makefile` para baixar a image está descontinuada. E também tive problemas ao digitar os comandos: `minikube -p dev.to start --cpus 2 --memory=4096`; `minikube -p dev.to addons enable ingress` e `minikube -p dev.to addons enable metrics-server`.  
  - **Solução**: Sempre ao abri o terminal digitar o comando: `sudo usermod -aG docker $USER && newgrp docker` pois descarta o uso do `sudo` ao chamar o `docker` no terminal e porque o `minikube` dá erro quando é preciso usar o `sudo` juntamente do `docker`.

## Boas Praticas

- Use imagens  **JRE** e não **JDK**;
- Automatize tudo que for possivel;
-  Use Variaveis de Ambiente;
- Sempre tenha o *Health Check*, pois se a aplicação não estiver no ar o **Kubernetes** mostrará que a aplicação está *Ready*.
- Sempre procure pelas informações da aplicação;
- Usar tecnicas de monitoramento e *log* (e em toda transação tenha o *trace*).