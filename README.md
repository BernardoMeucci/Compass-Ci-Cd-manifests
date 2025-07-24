# 📄 Repositório de Manifestos Kubernetes

![Status](https://img.shields.io/badge/gerenciado_por-ArgoCD-EF7B4D?style=for-the-badge&logo=argo&logoColor=white)
![Infraestrutura](https://img.shields.io/badge/infra_como-código-blueviolet?style=for-the-badge)

Este repositório atua como a **fonte única da verdade** para a implantação da aplicação FastAPI no ambiente Kubernetes, seguindo as melhores práticas de GitOps.

## 🎯 Propósito

O conteúdo deste repositório descreve o estado desejado da aplicação no cluster. Ele não contém código-fonte, apenas os manifestos declarativos do Kubernetes.

- **`deployment.yaml`**: Define como a aplicação deve ser executada, qual imagem Docker utilizar e o número de réplicas.
- **`service.yaml`**: Define como a aplicação é exposta na rede interna do cluster.

## 🔄 Fluxo de Atualização

Este repositório é atualizado **automaticamente** pela pipeline de CI/CD configurada no repositório da aplicação principal:

> **[Compass-Ci-Cd](https://github.com/BernardoMeucci/Compass-Ci-Cd)**

Qualquer alteração na imagem da aplicação aciona um `commit` automático aqui, que por sua vez é detectado e sincronizado pelo **ArgoCD** para realizar o deploy no cluster.