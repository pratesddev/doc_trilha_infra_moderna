# 🏢 Plano de Estudos: Infraestrutura Moderna para Gestão de Datacenter

Guia para quem está começando do zero e quer chegar à gestão de datacenters modernos (físicos, híbridos e em nuvem).

> **Duração estimada:** 9 a 12 meses, com 8 a 10 horas por semana.
> **Pré-requisito:** nenhum. Curiosidade e disciplina bastam.

---

## 📌 Como usar este guia

1. Siga as fases **em ordem**: cada uma sustenta a seguinte.
2. Em cada fase, estude a teoria, **pratique em laboratório** e só então avance.
3. Faça a certificação da fase **somente se fizer sentido para sua meta**; o conhecimento vale mais que o certificado.
4. Documente seus laboratórios em um repositório no GitHub. Isso vira portfólio.

---

## 🗺️ Visão geral das fases

| Fase | Tema | Duração |
| ------ | ------ | --------- |
| 0 | Fundamentos de TI | 3 a 4 semanas |
| 1 | Redes | 8 a 10 semanas |
| 2 | Linux e servidores | 8 semanas |
| 3 | Virtualização e armazenamento | 6 a 8 semanas |
| 4 | Infraestrutura física do datacenter | 6 semanas |
| 5 | Nuvem e infraestrutura como código | 8 a 10 semanas |
| 6 | Contêineres e Kubernetes | 6 a 8 semanas |
| 7 | Monitoramento, SRE e operações | 6 semanas |
| 8 | Segurança, continuidade e gestão | 6 semanas |

---

## 🔹 Fase 0: Fundamentos de TI

O que estudar

- Como um computador funciona: CPU, memória, disco, placa-mãe, BIOS/UEFI
- Sistemas de numeração (binário, hexadecimal)
- Noções de sistemas operacionais (Windows e Linux)
- Conceitos básicos de lógica e scripts simples

Prática

- Montar e desmontar um computador (ou assistir a montagens detalhadas)
- Instalar Windows e Linux em máquina virtual (VirtualBox)

Certificação sugerida

- 🆓 Cursos gratuitos de fundamentos: Cisco Networking Academy (ex.: *Introduction to IT*), Microsoft Learn
- 💰 CompTIA A+ *(opcional; útil para quem nunca teve contato com hardware)*

---

## 🔹 Fase 1: Redes

A rede é o coração do datacenter. Dedique tempo extra aqui.

O que estudar

- Modelos OSI e TCP/IP
- Endereçamento IPv4 e IPv6, sub-redes (CIDR, VLSM)
- Ethernet, switching, VLANs, trunking, STP
- Roteamento: estático, OSPF e BGP (noções)
- DNS, DHCP, NAT, firewall, VPN
- Conceitos de datacenter: topologia **leaf-spine**, VXLAN, redundância (LACP, VRRP)

Prática

- Simular redes no **Cisco Packet Tracer** (gratuito) ou **GNS3/EVE-NG**
- Configurar VLANs, roteamento e DHCP em laboratório
- Usar Wireshark para analisar tráfego

Certificação sugerida

- 🆓 Cisco Networking Academy: *Networking Basics* e *Switching, Routing and Wireless Essentials* (cursos gratuitos com certificado de conclusão)
- 💰 **CompTIA Network+** (neutra de fabricante) **ou** **Cisco CCNA** (mais reconhecida no mercado e mais profunda). Escolha **uma** delas.

---

## 🔹 Fase 2: Linux e servidores

O que estudar

- Linha de comando, sistema de arquivos, permissões
- Gerenciamento de usuários, processos e serviços (systemd)
- Pacotes, logs, cron
- Rede no Linux (ip, ss, firewalld/iptables/nftables)
- SSH, chaves e hardening básico
- Shell script (Bash) e introdução a Python
- Hardware de servidor: BMC/iDRAC/iLO, RAID, fontes redundantes, firmware

Prática

- Montar um servidor Linux (Ubuntu Server ou Rocky/AlmaLinux) em VM
- Automatizar tarefas com scripts
- Subir serviços: web (Nginx), DNS, banco de dados

Certificação sugerida

- 🆓 **Linux Foundation: Introduction to Linux** (curso gratuito) e Linux Journey (site gratuito)
- 💰 **Red Hat RHCSA** (muito valorizada em ambientes corporativos) **ou** **CompTIA Linux+**
- 💰 *Opcional:* **CompTIA Server+** (foco em hardware e administração de servidores)

---

## 🔹 Fase 3: Virtualização e armazenamento

O que estudar

- Hypervisors: KVM, VMware vSphere/ESXi, Hyper-V, Proxmox
- Conceitos: VMs, snapshots, clusters, alta disponibilidade, migração ao vivo
- Armazenamento: DAS, NAS, SAN, iSCSI, NFS, Fibre Channel
- RAID, SSD/NVMe, IOPS, latência, throughput
- Backup (regra 3-2-1), replicação e recuperação de desastres
- Conceitos de HCI (infraestrutura hiperconvergente) e Ceph

Prática

- Instalar **Proxmox VE** (gratuito) e criar um cluster de teste
- Configurar um storage NFS/iSCSI
- Testar backup e restauração de uma VM

Certificação sugerida

- 🆓 Laboratórios e documentação oficial do Proxmox, KVM e VMware (Hands-on Labs)
- 💰 **VMware VCP-DCV** *(somente se sua empresa-alvo usar VMware)*

---

## 🔹 Fase 4: Infraestrutura física do datacenter

Diferencial de quem trabalha com gestão de datacenter.

O que estudar

- Classificação de datacenters: **Tiers I a IV** (Uptime Institute), TIA-942
- Energia: entrada de energia, UPS, geradores, PDUs, redundâncias (N, N+1, 2N)
- Refrigeração: CRAC/CRAH, corredor quente e frio, contenção, free cooling, resfriamento líquido
- **PUE** e métricas de eficiência
- Racks, cabeamento estruturado (cobre e fibra), organização e identificação
- Proteção contra incêndio, controle de acesso, segurança física
- DCIM (gestão de infraestrutura de datacenter) e planejamento de capacidade

Prática

- Desenhar um layout de sala técnica com 10 racks (energia, refrigeração e cabeamento)
- Calcular carga elétrica por rack e PUE de um cenário fictício

Certificação sugerida

- 🆓 **Schneider Electric Data Center University** (cursos gratuitos sobre energia, refrigeração e operação)
- 💰 **CDCP (Certified Data Centre Professional, EPI)**: ótima porta de entrada
- 💰 **Uptime Institute ATD/AOS** (projeto e operações de Tier): para quem quer se aprofundar, é a referência do setor

---

## 🔹 Fase 5: Nuvem e infraestrutura como código

O que estudar

- Modelos IaaS, PaaS, SaaS; nuvem pública, privada e híbrida
- Serviços essenciais: computação, armazenamento, rede, IAM, balanceamento
- Custos e modelo de responsabilidade compartilhada
- **Git** e fluxo de trabalho com GitHub
- **Terraform** (provisionamento) e **Ansible** (configuração)
- Introdução a CI/CD

Prática

- Criar uma conta gratuita em um provedor (AWS, Azure ou Google Cloud) e montar uma VPC com VMs
- Provisionar a mesma infraestrutura com Terraform
- Configurar servidores com playbooks Ansible

Certificação sugerida

- 🆓 Treinamentos gratuitos: **AWS Skill Builder**, **Microsoft Learn**, **Google Cloud Skills Boost**
- 💰 **AWS Cloud Practitioner** *ou* **Microsoft AZ-900** (fundamentos); depois, se quiser avançar, uma associate (ex.: AWS Solutions Architect Associate)
- 💰 **HashiCorp Terraform Associate**

---

## 🔹 Fase 6: Contêineres e Kubernetes

O que estudar

- Docker: imagens, volumes, redes, Compose
- Conceitos de orquestração
- Kubernetes: Pods, Deployments, Services, Ingress, ConfigMaps/Secrets, volumes persistentes
- Helm e noções de GitOps

Prática

- Conteinerizar uma aplicação simples
- Subir um cluster local (kind, minikube ou k3s) e fazer deploy
- Montar um cluster com k3s em 3 VMs

Certificação sugerida

- 🆓 Kubernetes Basics (tutoriais oficiais) e curso gratuito *Introduction to Kubernetes* (Linux Foundation)
- 💰 **CKA (Certified Kubernetes Administrator)**: prova prática e muito respeitada

---

## 🔹 Fase 7: Monitoramento, SRE e operações

O que estudar

- Observabilidade: métricas, logs e traces
- **Prometheus + Grafana**, Zabbix, Loki/ELK
- SLI, SLO, SLA e error budget
- Gestão de incidentes, postmortems e runbooks
- ITIL (conceitos): gestão de incidentes, problemas e mudanças
- Automação de tarefas operacionais

Prática

- Monitorar seu laboratório com Prometheus e Grafana e criar alertas
- Simular um incidente e escrever um postmortem

Certificação sugerida

- 🆓 Livro **Site Reliability Engineering** (Google, leitura gratuita online) e cursos introdutórios de ITIL/observabilidade
- 💰 **ITIL 4 Foundation** *(opcional; relevante para ambientes corporativos e de gestão de serviços)*

---

## 🔹 Fase 8: Segurança, continuidade e gestão

O que estudar

- Fundamentos de segurança: CIA, defesa em profundidade, segmentação, zero trust
- IAM, gestão de vulnerabilidades e patches
- Normas e frameworks: ISO 27001, ISO 22301 (continuidade), LGPD
- Plano de continuidade e recuperação de desastres (RTO/RPO)
- Gestão de fornecedores, contratos, SLAs e orçamento (CAPEX/OPEX)
- Sustentabilidade e eficiência energética

Prática

- Escrever um plano de DR para o seu laboratório
- Fazer uma análise de riscos simples de um datacenter fictício

Certificação sugerida

- 🆓 **Fortinet NSE 1 a 3** e **ISC2 Certified in Cybersecurity (CC)**, que tem treinamento e exame gratuitos em condições promocionais do programa (confirme a disponibilidade atual no site oficial)
- 💰 **CompTIA Security+** (porta de entrada em segurança)

---

## 🏆 Resumo: certificações essenciais

### 🆓 Gratuitas

| Certificação / curso | Área |
| --- | --- |
| Cisco Networking Academy (cursos com certificado de conclusão) | Redes |
| Linux Foundation: Introduction to Linux / Kubernetes | Linux e contêineres |
| Schneider Electric Data Center University | Infraestrutura física |
| AWS Skill Builder / Microsoft Learn / Google Cloud Skills Boost | Nuvem |
| Fortinet NSE 1 a 3 | Segurança |
| ISC2 Certified in Cybersecurity (verificar disponibilidade) | Segurança |

### 💰 Pagas (priorize na ordem)

| Ordem | Certificação | Por quê |
| --- | --- | --- |
| 1 | **CCNA** *ou* **Network+** | Base sólida de redes |
| 2 | **RHCSA** *ou* **Linux+** | Administração Linux |
| 3 | **CDCP** | Fundamentos de datacenter |
| 4 | **AWS Cloud Practitioner** *ou* **AZ-900** | Nuvem |
| 5 | **Terraform Associate** | Infraestrutura como código |
| 6 | **CKA** | Kubernetes |
| 7 | **Uptime Institute ATD/AOS** | Especialização em datacenter |

> ⚠️ Valores, formatos e disponibilidade de exames mudam com frequência. Confira sempre o site oficial de cada certificação antes de investir.

---

## 🧪 Projeto final (portfólio)

Monte um **mini datacenter virtual** documentado no GitHub:

- Rede segmentada em VLANs (Packet Tracer ou EVE-NG)
- Cluster Proxmox com 2 ou 3 nós e armazenamento compartilhado
- Servidores Linux provisionados com Terraform e Ansible
- Cluster k3s com uma aplicação em contêineres
- Monitoramento com Prometheus e Grafana
- Documento de **projeto físico** (energia, refrigeração, layout de racks)
- Plano de **backup e DR** com RTO/RPO definidos

---

## 📚 Recursos gratuitos recomendados

- **Redes:** Cisco Packet Tracer, Professor Messer (vídeos), Wireshark
- **Linux:** Linux Journey, OverTheWire (Bandit), documentação da Red Hat
- **Virtualização:** documentação do Proxmox, VMware Hands-on Labs
- **Datacenter:** Schneider Electric Data Center University, materiais públicos da Uptime Institute e do Open Compute Project (OCP)
- **Nuvem e DevOps:** documentação oficial, KodeKloud (conteúdo gratuito), Roadmap.sh
- **SRE:** *Site Reliability Engineering* e *The SRE Workbook* (Google)

---

## ✅ Checklist de progresso

- [ ] Fase 0: Fundamentos de TI
- [ ] Fase 1: Redes
- [ ] Fase 2: Linux e servidores
- [ ] Fase 3: Virtualização e armazenamento
- [ ] Fase 4: Infraestrutura física do datacenter
- [ ] Fase 5: Nuvem e IaC
- [ ] Fase 6: Contêineres e Kubernetes
- [ ] Fase 7: Monitoramento, SRE e operações
- [ ] Fase 8: Segurança, continuidade e gestão
- [ ] Projeto final publicado no GitHub

---

## 💡 Dicas finais

- **Laboratório antes de certificado.** Quem pratica aprende; quem só decora esquece.
- **Documente tudo.** Escrever o que aprendeu fixa o conteúdo e gera portfólio.
- **Uma certificação por vez.** Evite acumular várias ao mesmo tempo.
- **Participe de comunidades** (Discord, Reddit, grupos de Telegram/WhatsApp de infra) e acompanhe projetos open source.
- **Revise o plano a cada trimestre.** A tecnologia muda rápido; ajuste conforme seus objetivos.
