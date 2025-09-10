# ArgoCD Applications Repository

Este repositório centraliza todas as aplicações ArgoCD para deploy automático via App of Apps pattern.

## Estrutura

```
applications/
├── app-of-apps.yaml          # App principal que monitora todas as outras
├── example-app/              # Exemplo de aplicação
│   └── application.yaml
└── [service-name]/           # Cada serviço tem sua pasta
    └── application.yaml      # Manifest ArgoCD da aplicação
```

## Como Funciona

1. **Backstage** cria um novo microsserviço
2. **Template** adiciona automaticamente uma nova pasta em `applications/[service-name]/`
3. **App of Apps** detecta a nova aplicação e a registra no ArgoCD
4. **ArgoCD** faz o deploy automático do microsserviço

## App of Apps

O arquivo `app-of-apps.yaml` monitora este repositório e cria automaticamente todas as aplicações encontradas na pasta `applications/`.

## Monitoramento

- **ArgoCD Dashboard**: https://argocd.gruppy.com.br
- **Apps Repository**: https://github.com/LinkedFarma/argocd-applications
