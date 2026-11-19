# 🏗️ Trilha Infra Moderna – Roteiro de Estudos

**Objetivo:** Transformar a experiência em Datacenter/Telecom em uma carreira em **Cloud Engineering, SRE e Platform Engineering**, com baixo custo, 3 certificações estratégicas e um portfólio no GitHub que prove raciocínio técnico.

> ✅ Concluído · 🟡 Em andamento · ⏳ Planejado

**Duração estimada:** 8 meses  
**Carga semanal:** 8–12 horas  
**Carga total:** ≈ 275 a 410 horas

---

## 📍 Visão Geral da Trilha

| Mês | Foco principal | Ferramentas-chave | Entrega principal | Certificação |
| ----- | ---------------- | ------------------- | ------------------- | -------------- |
| **1** | Linux, redes aplicadas, Git, Bash/Python, Docker | Linux, Git, Docker, Bandit | Repo-base + app Dockerizada + scripts | — |
| **2** | AWS Core (conta criada neste mês) | IAM, VPC, EC2, ALB, ASG, S3, RDS | Arquitetura 3 camadas (console + diagrama) | Preparação SAA |
| **3** | Terraform + AWS | Terraform, módulos, remote state | Arquitetura do Mês 2 em código | **SAA** e/ou **Terraform Associate** |
| **4** | Kubernetes fundamentos | kind/k3s, kubectl, Helm, Kustomize | App em K8s local com Helm | — |
| **5** | Kubernetes intermediário / admin | Ingress/Gateway, PV, HPA, NetworkPolicy, RBAC | App completa + troubleshooting | Preparação CKA |
| **6** | CI/CD + GitOps + segurança | GitHub Actions, Argo CD/Flux, Trivy, OIDC | Pipeline commit → cluster | **CKA** |
| **7** | Observabilidade + SRE | Prometheus, Grafana, Loki, Alertmanager | SLOs, alertas por error budget, post-mortem | — |
| **8** | Capstone + portfólio + candidaturas | Tudo integrado | Plataforma completa + documentação | Opcional (PCA / CGOA) |

> **Regra de ouro:** Semanas 1–3 do mês = aprender. Semana 4 = projeto + documentação + revisão.

---

## 01. Mês 1 — Fundamentos (Linux, redes, Git, scripting, Docker)

**Objetivo:** Nivelar o que falta e dominar o ambiente de trabalho **sem gastar nada**.

**Conteúdo essencial:**

- Linux: systemd, journald, processos, permissões, `ss`, `ip`, `tcpdump`, `strace`, `dig`, `mtr`
- Redes aplicadas à nuvem: DNS, TLS, HTTP/2, CIDR, Security Groups vs NACL
- Git: branches, rebase, PR, conventional commits
- Bash: funções, `set -euo pipefail`, `jq`, `curl`
- Python básico para automação
- Docker: imagem, container, Dockerfile, volumes, redes, Compose, multi-stage, usuário não-root, Trivy

**Projeto do mês — “Fundação”:**

- Repositório `infra-portfolio` com estrutura padrão
- App simples (Node/Python/Go) dockerizada com Compose
- 2 scripts Bash úteis (health-check, backup com rotação)
- README completo

**Critério de pronto:** consigo explicar o que acontece do `docker run` até o processo no kernel e diagnosticar um problema de rede só com `ss`/`tcpdump`/`dig`.

---

## 02. Mês 2 — AWS Core

> Crie a conta AWS **no início deste mês**. Use o Free plan, configure Budgets e MFA no root no primeiro dia.

**Conteúdo essencial:**

- IAM (usuários, roles, policies, least privilege, Identity Center)
- VPC completa (subnets públicas/privadas, IGW, NAT, route tables, SG vs NACL, VPC endpoints)
- EC2, AMIs, EBS, user data, ALB/NLB, Auto Scaling
- S3 (versionamento, lifecycle, policies, criptografia)
- RDS (Single-AZ), Route 53, CloudWatch básico
- Well-Architected Framework

**Projeto do mês — “3 camadas”:**

- VPC multi-AZ com subnets públicas e privadas
- ALB → ASG (2 EC2) → RDS em subnet privada → S3
- Acesso via **SSM Session Manager** (sem SSH aberto)
- Diagrama + passo a passo + custo estimado

> **Atenção a custos:** NAT Gateway, ALB e IPv4 público cobram por hora. Destrua ao final de cada sessão.

**Critério de pronto:** consigo desenhar de memória uma VPC multi-AZ e justificar cada rota e cada regra de Security Group.

---

## 03. Mês 3 — Terraform (IaC) aplicado à AWS

**Objetivo:** Recriar o Mês 2 como código, com boas práticas.

**Conteúdo essencial:**

- Providers, resources, data sources, variáveis, outputs, locals, `for_each`/`count`
- Módulos e versionamento
- State remoto (S3) + locking
- `terraform plan` em PR, tflint, fmt/validate, Checkov/Trivy
- `terraform import` e drift
- Conhecer OpenTofu

**Projeto do mês — “Mês 2 em código”:**

- Estrutura `modules/` + `envs/dev`
- Remote state + `make up` / `make down`
- Pipeline simples de fmt + validate + plan no GitHub Actions

**Certificações do mês:**

- **AWS Solutions Architect – Associate (SAA)** → 🔴 Paga + Obrigatória
- **HashiCorp Terraform Associate** → 🔴 Paga + Obrigatória

**Critério de pronto:** destruo e recrio a arquitetura inteira com um único comando, sem tocar no console.

---

## 04. Mês 4 — Kubernetes: Fundamentos

**Conteúdo essencial:**

- Arquitetura (control plane, kubelet, etcd, scheduler, CNI, CSI)
- Pod, ReplicaSet, Deployment, Service, Namespace, Labels
- ConfigMap, Secret, probes, requests/limits
- `kubectl` fluente
- **Helm** e **Kustomize**
- Cluster local: kind ou k3s

**Projeto do mês — “App no K8s com Helm”:**

- App com 2 serviços + banco
- Chart Helm próprio com `values-dev.yaml`
- Rollout e rollback documentados

**Critério de pronto:** consigo subir um cluster do zero, fazer deploy e explicar o caminho de um request até o Pod.

---

## 05. Mês 5 — Kubernetes: Intermediário / Administração (preparação CKA)

**Conteúdo essencial:**

- Ingress e Gateway API
- PV/PVC/StorageClass, StatefulSet
- HPA, PDB, taints/tolerations, affinity
- RBAC, ServiceAccounts, NetworkPolicy, Pod Security Standards
- Administração: kubeadm, upgrade, backup/restore do etcd
- Troubleshooting avançado (CrashLoopBackOff, ImagePullBackOff, Pending, NotReady, DNS)

**Projeto do mês — “App de produção no K8s”:**

- Ingress/Gateway com TLS (cert-manager)
- HPA, NetworkPolicy deny-by-default, RBAC mínimo
- Relatório “5 incidentes que provoquei e como resolvi”

**Critério de pronto:** resolvo cenários de troubleshooting do Killercoda/simulador em menos de 10 minutos cada.

---

## 06. Mês 6 — CI/CD + GitOps + Supply Chain

**Conteúdo essencial:**

- GitHub Actions (matrix, cache, reusable workflows, environments)
- **OIDC GitHub → AWS** (zero chaves estáticas)
- Build → test → scan (Trivy) → push → assinar (cosign opcional)
- GitOps com **Argo CD** ou **Flux**
- Gestão de segredos (External Secrets, SOPS ou Sealed Secrets)
- Estratégias de deploy (rolling, blue/green, canary)

**Projeto do mês — “Commit → Produção”:**

- Push no `main` → pipeline → imagem → PR automático de manifests → Argo CD sincroniza
- Dependabot/Renovate ativos

**Certificação do mês:**

- **CKA (Certified Kubernetes Administrator)** → 🔴 Paga + Obrigatória

---

## 07. Mês 7 — Observabilidade + SRE

### Observabilidade

- Prometheus (PromQL, recording rules, ServiceMonitor)
- Grafana (dashboards como código)
- Loki (logs) + noções de OpenTelemetry (traces)
- Método RED/USE e os 4 golden signals

### SRE

- SLI, SLO, Error Budget, burn rate alerts
- Toil e automação
- Gestão de incidentes, on-call, runbooks
- Post-mortem blameless
- Capacity planning (sua vantagem de Datacenter)
- Chaos engineering básico

**Projeto do mês — “Confiabilidade”:**

- Definir 2 SLIs / 2 SLOs
- Alertas por burn rate
- Injetar falha e simular incidente com cronômetro
- Escrever post-mortem blameless

---

## 08. Mês 8 — Capstone + Portfólio + Candidaturas

### Capstone — “Plataforma completa”

- Infra em Terraform (VPC + cluster + ECR)
- Aplicação containerizada (2–3 serviços)
- CI/CD com GitHub Actions + OIDC + scan
- GitOps (Argo CD ou Flux)
- Observabilidade completa (Prometheus + Grafana + Loki + Alertmanager)
- SLOs + alertas por burn rate + runbooks
- Diagrama de arquitetura + ADRs
- Vídeo curto (3–5 min) demonstrando subir, usar e destruir
- Estimativa de custo + `terraform destroy` documentado

### Outras atividades

- Revisar todos os READMEs e diagramas
- Publicar artigo técnico (LinkedIn / dev.to)
- Atualizar currículo e LinkedIn
- 10 candidaturas/semana + simulação de entrevistas

---

## 🏅 Certificações da Trilha (alinhadas ao README)

**Legenda:**

- 🟢 Gratuita + Recomendada
- 🔵 Paga + Recomendada
- 🔴 Paga + Obrigatória

### Prioridade alta (fazer durante os 8 meses)

| Certificação | Tipo | Custo estimado | Quando fazer |
| -------------- | ------ | ---------------- | -------------- |
| AWS Solutions Architect – Associate (SAA) | 🔴 Paga + Obrigatória | US$ 150 | Fim do Mês 3 |
| HashiCorp Terraform Associate | 🔴 Paga + Obrigatória | ~US$ 70,50 + impostos | Mês 3–4 |
| CKA (Certified Kubernetes Administrator) | 🔴 Paga + Obrigatória | US$ 445 (promoções frequentes) | Fim do Mês 6 |

### Recomendadas / Opcionais

| Certificação | Tipo | Custo estimado | Observação |
| -------------- | ------ | ---------------- | ------------ |
| AWS Cloud Practitioner | 🔵 Paga + Recomendada | US$ 100 | Opcional (pode pular se já tiver base) |
| KCNA | 🔵 Paga + Recomendada | ~US$ 250 | Útil se faltar confiança antes da CKA |
| LFCS | 🔵 Paga + Recomendada | US$ 445 | Bom reforço de Linux |
| PCA (Prometheus) | 🔵 Paga + Recomendada | Verificar | Mês 8 se sobrar tempo |
| CGOA (GitOps) | 🔵 Paga + Recomendada | Verificar | Mês 8 se sobrar tempo |
| CKS | 🔵 Paga + Recomendada | US$ 445 | Pós-plano (exige CKA válida) |

> **Estratégia:** foque em **3 certificações** (SAA + Terraform Associate + CKA). Mais que isso rouba tempo de portfólio.

---

## 📂 Estrutura recomendada do portfólio

```text
infra-portfolio/
├── README.md
├── 01-fundacao/
├── 02-aws-3-camadas/
├── 03-terraform-modular/
├── 04-k8s-helm/
├── 05-k8s-producao/
├── 06-gitops-pipeline/
├── 07-observabilidade-sre/
├── 08-capstone/
└── docs/
    ├── adr/
    └── postmortems/
```

Cada projeto deve ter:

- Diagrama de arquitetura
- Decisões técnicas (ADRs)
- Como subir / validar / destruir
- Custos estimados
- Lições aprendidas

---

## 💰 Controle de custos (checklist importante)

- [ ] MFA no root + usuário administrativo via IAM Identity Center
- [ ] AWS Budgets com alertas (US$ 5, 10 e 20)
- [ ] Tags obrigatórias (`project`, `owner`, `env`)
- [ ] Nenhum recurso sem `terraform destroy` no fim da sessão
- [ ] Kubernetes **local** no dia a dia (kind/k3s). EKS só no capstone, por poucas horas
- [ ] Revisar semanalmente: NAT Gateway, ALB, IPs públicos, volumes órfãos
- [ ] Antes do Mês 8: decidir sobre migração para Paid plan

> **Atenção (2025/2026):** Contas Free Tier novas recebem créditos limitados e podem ser encerradas após 6 meses. Crie a conta só no Mês 2 e monitore de perto.

---

## 💡 Dicas finais

- **Portfólio > Certificação.** Mostre decisões, trade-offs, incidentes simulados e custos.
- Sua experiência de Datacenter é um diferencial forte (capacidade, disponibilidade, mudanças, incidentes). Use isso nos projetos e nas entrevistas.
- Cada semana deve terminar com pelo menos um commit no GitHub.
- Documente tudo o que quebrar — esse é o valor real do repositório.

---

⭐ Continue registrando a jornada. O progresso acumulado é o que realmente conta.
