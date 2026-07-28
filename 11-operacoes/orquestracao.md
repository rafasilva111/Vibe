# Orquestração (Kubernetes)

## Propósito
Definir a configuração de orquestração Kubernetes.

## Recursos

| Recurso | Configuração |
|---|---|
| **Cluster** | EKS / AKS / GKE (3 AZ) |
| **Node Groups** | On-demand (base) + Spot (burst) |
| **Auto-scaling** | Cluster Autoscaler + HPA |
| **Networking** | Calico / Cilium |
| **Ingress** | NGINX Ingress Controller |
| **Service Mesh** | Istio (futuro) |

## Namespaces

| Namespace | Conteúdo |
|---|---|
| `plataforma` | Serviços core da plataforma |
| `dominios` | Serviços de domínio |
| `infra` | Infraestrutura (monitorização, logging) |
| `integracao` | Serviços de integração |
