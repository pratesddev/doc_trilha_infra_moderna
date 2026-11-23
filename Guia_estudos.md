# ✅ Guia de Estudos em Checklist: Infraestrutura Moderna para Gestão de Datacenter

Marque cada item com `[x]` conforme avançar. O formato funciona no Obsidian, no GitHub e no Notion (ao colar como lista de tarefas).

**Legenda:** 🆓 gratuito · 💰 pago · 🇧🇷 português · 🇺🇸 inglês
**Ritmo:** 8 a 10 h/semana · **Duração total:** cerca de 10 meses

> Em cada fase as etapas seguem a mesma ordem: **1) Entender → 2) Estudar com curso → 3) Ler → 4) Praticar → 5) Revisar → 6) Entregar → 7) Certificar (opcional)**.
> Na Udemy, use as palavras-chave indicadas, filtre por **português**, nota igual ou superior a 4,5 e atualização recente.

---

## 📊 Painel de progresso

| Fase | Tema | Prazo | Status |
| --- | --- | --- | --- |
| 0 | Fundamentos de TI | 3 a 4 semanas | ⬜ |
| 1 | Redes | 8 a 10 semanas | ⬜ |
| 2 | Linux e servidores | 8 semanas | ⬜ |
| 3 | Virtualização e armazenamento | 6 a 8 semanas | ⬜ |
| 4 | Infraestrutura física do datacenter | 6 semanas | ⬜ |
| 5 | Nuvem e infraestrutura como código | 8 a 10 semanas | ⬜ |
| 6 | Contêineres e Kubernetes | 6 a 8 semanas | ⬜ |
| 7 | Monitoramento, SRE e operações | 6 semanas | ⬜ |
| 8 | Segurança, continuidade e gestão | 6 semanas | ⬜ |

---

## 🛠️ Etapa preparatória: ambiente de estudo

- [ ] Criar o repositório no GitHub `lab-infra-datacenter` (uma pasta por fase)
- [ ] Instalar VirtualBox (ou Proxmox, se tiver máquina dedicada)
- [ ] Instalar Cisco Packet Tracer (🆓, requer cadastro na Cisco Networking Academy)
- [ ] Instalar uma VM Linux (Ubuntu Server ou Rocky/AlmaLinux)
- [ ] Criar um caderno de anotações (Obsidian ou Notion) com uma página por fase
- [ ] Reservar horários fixos na agenda (mínimo de 4 blocos por semana)

---

## 🔹 Fase 0: Fundamentos de TI

**Objetivo:** entender como um computador e um sistema operacional funcionam.

- [ ] **1. Entender:** CPU, memória, armazenamento, BIOS/UEFI, binário e hexadecimal
- [ ] **2. Curso:** 🆓🇧🇷 Fundação Bradesco (Escola Virtual) ou Microsoft Learn em português · 💰🇧🇷 Udemy: "Fundamentos de TI", "Introdução à infraestrutura de TI"
- [ ] **3. Ler:** *Organização Estruturada de Computadores* (Tanenbaum), capítulos introdutórios
- [ ] **4. Praticar:** instalar Windows e Linux em VM; explorar o BIOS/UEFI da VM
- [ ] **5. Revisar:** resumo de 1 página sobre o caminho de um dado entre CPU, memória e disco
- [ ] **6. Entregar:** anotações da fase no repositório
- [ ] **7. Certificar (opcional):** 💰 CompTIA A+ (só se precisar de base de hardware)

---

## 🔹 Fase 1: Redes

**Objetivo:** projetar, configurar e diagnosticar redes (a base do datacenter).

- [ ] **1. Entender:** modelos OSI e TCP/IP, IPv4/IPv6, sub-redes (CIDR e VLSM)
- [ ] **2. Entender:** Ethernet, switching, VLANs, trunking, STP, LACP
- [ ] **3. Entender:** roteamento estático, OSPF e BGP (noções), DNS, DHCP, NAT
- [ ] **4. Entender (datacenter):** topologia leaf-spine e VXLAN
- [ ] **5. Curso:** 🆓🇧🇷 Cisco Networking Academy (*Networking Basics* e *Switching, Routing and Wireless Essentials*) · 🆓🇺🇸 Jeremy's IT Lab (CCNA) e Professor Messer (Network+) · 💰🇧🇷 Udemy: "CCNA 200-301", "Redes de computadores do zero", "Subnetting"
- [ ] **6. Ler:** *Redes de Computadores* (Tanenbaum) ou *Redes de Computadores e a Internet* (Kurose e Ross) · 🇺🇸 *CCNA 200-301 Official Cert Guide* (Odom)
- [ ] **7. Praticar:** montar no Packet Tracer ou EVE-NG uma rede com 3 VLANs, roteamento entre VLANs, DHCP e ACL
- [ ] **8. Praticar:** capturar e analisar tráfego (DNS, DHCP, TCP handshake) no Wireshark
- [ ] **9. Revisar:** fazer 20 exercícios de sub-redes sem consulta
- [ ] **10. Entregar:** topologia documentada com diagrama e configurações no GitHub
- [ ] **11. Certificar (opcional):** 💰 CCNA **ou** CompTIA Network+ (escolha uma)

---

## 🔹 Fase 2: Linux e servidores

**Objetivo:** administrar servidores Linux pela linha de comando.

- [ ] **1. Entender:** sistema de arquivos, permissões, usuários e grupos
- [ ] **2. Entender:** processos, systemd, pacotes, logs e cron
- [ ] **3. Entender:** rede no Linux (ip, ss, firewall), SSH com chaves
- [ ] **4. Entender:** hardware de servidor (BMC/iDRAC/iLO, RAID, fontes redundantes, firmware)
- [ ] **5. Curso:** 🆓🇧🇷 Red Hat RH024 (*Linux Technical Overview*) · 🆓🇧🇷 LabEx (laboratórios guiados) · 🆓🇺🇸 Linux Journey e curso *Introduction to Linux* (Linux Foundation) · 💰🇧🇷 Udemy: "Linux do zero ao administrador", "Shell Script", "RHCSA"
- [ ] **6. Ler:** *A Linha de Comando do Linux* (Shotts, Novatec)
- [ ] **7. Praticar:** OverTheWire Bandit (🆓) até o nível 15
- [ ] **8. Praticar:** servidor com Nginx, DNS (BIND ou dnsmasq) e banco de dados em VM, acessado só por SSH com chave
- [ ] **9. Praticar:** 3 scripts Bash (backup, verificação de serviços, relatório de disco)
- [ ] **10. Revisar:** refazer o servidor do zero em 1 hora, sem consulta
- [ ] **11. Entregar:** scripts e passo a passo no GitHub
- [ ] **12. Certificar (opcional):** 💰 RHCSA **ou** CompTIA Linux+ · 💰 CompTIA Server+ (foco em hardware)

---

## 🔹 Fase 3: Virtualização e armazenamento

**Objetivo:** consolidar servidores em hypervisors e entender como os dados são guardados e protegidos.

- [ ] **1. Entender:** hypervisors tipo 1 e 2, VMs, snapshots, clusters, alta disponibilidade, migração ao vivo
- [ ] **2. Entender:** DAS, NAS, SAN, iSCSI, NFS, Fibre Channel, RAID, SSD/NVMe, IOPS e latência
- [ ] **3. Entender:** backup (regra 3-2-1), replicação, RTO e RPO
- [ ] **4. Curso:** 🆓🇺🇸 Proxmox VE Admin Guide, VMware Hands-on Labs · 🆓🇧🇷 YouTube: "Proxmox cluster passo a passo" · 💰🇧🇷 Udemy: "Proxmox", "VMware vSphere", "Hyper-V"
- [ ] **5. Ler:** 🇺🇸 *Mastering Proxmox* (Wasim Ahmed) e documentação do Ceph
- [ ] **6. Praticar:** instalar o Proxmox (em máquina física ou com virtualização aninhada) e criar 3 VMs
- [ ] **7. Praticar:** configurar um storage NFS ou iSCSI e conectar ao hypervisor
- [ ] **8. Praticar:** simular a falha de um nó e testar a migração ou o reinício das VMs
- [ ] **9. Praticar:** fazer um backup e restaurar uma VM
- [ ] **10. Revisar:** explicar a diferença entre NAS, SAN e armazenamento hiperconvergente
- [ ] **11. Entregar:** documento do ambiente com diagrama
- [ ] **12. Certificar (opcional):** 💰 VMware VCP-DCV (só se o mercado-alvo usar VMware)

---

## 🔹 Fase 4: Infraestrutura física do datacenter

**Objetivo:** entender energia, refrigeração, cabeamento e níveis de disponibilidade.

- [ ] **1. Entender:** Tiers I a IV (Uptime Institute) e ANSI/TIA-942
- [ ] **2. Entender:** energia (entrada, UPS, gerador, PDU) e redundâncias N, N+1 e 2N
- [ ] **3. Entender:** refrigeração (CRAC/CRAH, corredor quente e frio, contenção, free cooling, líquida) e PUE
- [ ] **4. Entender:** racks, cabeamento estruturado (cobre e fibra), identificação e segurança física
- [ ] **5. Entender:** DCIM e planejamento de capacidade
- [ ] **6. Curso:** 🆓🇺🇸 Schneider Electric Data Center University · 🆓🇺🇸 Uptime Institute, Open Compute Project e The Green Grid (artigos) · 💰🇧🇷 Udemy: "Datacenter", "Cabeamento estruturado" (oferta em português limitada)
- [ ] **7. Ler:** 🇺🇸 *Data Center Handbook* (Hwaiyu Geng) · normas ABNT NBR 14565 e NBR 5410 (consulta)
- [ ] **8. Praticar:** desenhar o layout de uma sala com 10 racks, incluindo energia, refrigeração e cabeamento
- [ ] **9. Praticar:** calcular a carga elétrica por rack e o PUE de um cenário fictício
- [ ] **10. Revisar:** justificar a escolha do Tier para um caso (ex.: banco, hospital, pequena empresa)
- [ ] **11. Entregar:** projeto físico em PDF com memorial de cálculo
- [ ] **12. Certificar (opcional):** 💰 CDCP (EPI) · 💰 Uptime Institute ATD ou AOS

---

## 🔹 Fase 5: Nuvem e infraestrutura como código

**Objetivo:** provisionar e gerenciar infraestrutura por código, em nuvem e on-premises.

- [ ] **1. Entender:** IaaS, PaaS, SaaS, nuvem pública, privada e híbrida, responsabilidade compartilhada
- [ ] **2. Entender:** VPC, sub-redes, IAM, balanceadores, armazenamento de objetos e custos
- [ ] **3. Entender:** Git (branches, pull requests) e fluxo no GitHub
- [ ] **4. Entender:** Terraform (providers, state, módulos) e Ansible (inventário, playbooks, roles)
- [ ] **5. Curso:** 🆓🇧🇷 AWS Skill Builder (trilhas em português), Microsoft Learn (AZ-900 em português), Google Cloud Skills Boost · 🆓🇺🇸 HashiCorp Developer · 💰🇧🇷 Udemy: "AWS Cloud Practitioner", "AZ-900", "Terraform", "Ansible", "Git e GitHub"
- [ ] **6. Ler:** *Pro Git* (🆓, versão em português) · 🇺🇸 *Terraform: Up & Running* (Brikman)
- [ ] **7. Praticar:** criar conta gratuita em um provedor, montar VPC com 2 VMs e configurar alertas de custo
- [ ] **8. Praticar:** reproduzir a mesma infraestrutura com Terraform
- [ ] **9. Praticar:** configurar os servidores com um playbook Ansible
- [ ] **10. Revisar:** destruir e recriar tudo por código, sem cliques no console
- [ ] **11. Entregar:** repositório com código, diagrama e README
- [ ] **12. Certificar (opcional):** 💰 AWS Cloud Practitioner **ou** AZ-900 · 💰 HashiCorp Terraform Associate

---

## 🔹 Fase 6: Contêineres e Kubernetes

**Objetivo:** empacotar e orquestrar aplicações.

- [ ] **1. Entender:** imagens, contêineres, volumes, redes e Docker Compose
- [ ] **2. Entender:** Pods, Deployments, Services, Ingress, ConfigMaps, Secrets e volumes persistentes
- [ ] **3. Entender:** Helm e noções de GitOps
- [ ] **4. Curso:** 🆓🇧🇷 Descomplicando o Docker e o Kubernetes (GitHub da LinuxTips) · 🆓🇧🇷 documentação oficial do Kubernetes em português · 🆓🇺🇸 *Introduction to Kubernetes* (Linux Foundation), Killercoda · 💰🇧🇷 Udemy: "Docker e Kubernetes", "Kubernetes CKA", "Helm"
- [ ] **5. Ler:** *Kubernetes: Up & Running* (Novatec/O'Reilly)
- [ ] **6. Praticar:** conteinerizar uma aplicação simples e publicar a imagem
- [ ] **7. Praticar:** cluster local (kind, minikube ou k3s) com deploy, Service e Ingress
- [ ] **8. Praticar:** cluster k3s com 3 VMs do laboratório de Proxmox
- [ ] **9. Revisar:** diagnosticar um Pod com falha usando `describe`, `logs` e `events`
- [ ] **10. Entregar:** manifests e Helm chart no GitHub
- [ ] **11. Certificar (opcional):** 💰 CKA (prova prática; o simulador killer.sh acompanha a inscrição)

---

## 🔹 Fase 7: Monitoramento, SRE e operações

**Objetivo:** manter ambientes estáveis, visíveis e com resposta rápida a incidentes.

- [ ] **1. Entender:** métricas, logs e traces (observabilidade)
- [ ] **2. Entender:** SLI, SLO, SLA e error budget
- [ ] **3. Entender:** gestão de incidentes, problemas e mudanças (ITIL), runbooks e postmortems
- [ ] **4. Curso:** 🆓🇺🇸 livros gratuitos do Google em sre.google/books · 🆓🇧🇷 YouTube: "monitoramento com Prometheus e Grafana" · 🆓 documentação do Prometheus, Grafana e Zabbix · 💰🇧🇷 Udemy: "Zabbix", "Prometheus Grafana", "Observabilidade", "ITIL 4 Foundation"
- [ ] **5. Ler:** *SRE: Como o Google Administra seus Ambientes de Produção* (Novatec) e *O Projeto Fênix* (Alta Books)
- [ ] **6. Praticar:** monitorar o laboratório com Prometheus e Grafana
- [ ] **7. Praticar:** criar 3 alertas (CPU, disco cheio, serviço fora do ar)
- [ ] **8. Praticar:** simular um incidente e escrever o postmortem
- [ ] **9. Revisar:** definir SLOs para um serviço do laboratório
- [ ] **10. Entregar:** dashboards exportados e postmortem no GitHub
- [ ] **11. Certificar (opcional):** 💰 ITIL 4 Foundation

---

## 🔹 Fase 8: Segurança, continuidade e gestão

**Objetivo:** proteger o ambiente, planejar a continuidade e gerir o serviço.

- [ ] **1. Entender:** tríade CIA, defesa em profundidade, segmentação e zero trust
- [ ] **2. Entender:** IAM, gestão de vulnerabilidades e patches
- [ ] **3. Entender:** ISO 27001, ISO 22301 e LGPD
- [ ] **4. Entender:** plano de continuidade e recuperação de desastres (RTO e RPO)
- [ ] **5. Entender:** gestão de fornecedores, contratos, SLAs, CAPEX e OPEX
- [ ] **6. Curso:** 🆓 Fortinet NSE 1 a 3 · 🆓 ISC2 Certified in Cybersecurity (confira a oferta atual) · 🆓 Cisco Networking Academy (*Cybersecurity Essentials*) · 💰🇧🇷 Udemy: "Security+", "ISO 27001", "LGPD", "Plano de continuidade de negócios"
- [ ] **7. Ler:** guias da ANPD (LGPD) e cartilhas do CERT.br · 🇺🇸 *Security+ Study Guide* (Sybex)
- [ ] **8. Praticar:** análise de riscos de um datacenter fictício (matriz de probabilidade × impacto)
- [ ] **9. Praticar:** plano de DR do laboratório, com RTO e RPO definidos e testados
- [ ] **10. Revisar:** simular a falha de um site e cronometrar a recuperação
- [ ] **11. Entregar:** documento de análise de riscos e plano de DR
- [ ] **12. Certificar (opcional):** 💰 CompTIA Security+

---

## 🏁 Projeto final (portfólio)

- [ ] Rede segmentada em VLANs (Packet Tracer ou EVE-NG)
- [ ] Cluster Proxmox com armazenamento compartilhado
- [ ] Servidores Linux provisionados com Terraform e Ansible
- [ ] Cluster k3s com aplicação em contêineres
- [ ] Monitoramento com Prometheus e Grafana
- [ ] Projeto físico (energia, refrigeração e layout de racks)
- [ ] Plano de backup e DR com RTO e RPO testados
- [ ] README do projeto com diagramas e resultados

---

## 🎓 Certificações: ordem de prioridade (essenciais)

- [ ] 1. 💰 CCNA **ou** Network+
- [ ] 2. 💰 RHCSA **ou** Linux+
- [ ] 3. 💰 CDCP
- [ ] 4. 💰 AWS Cloud Practitioner **ou** AZ-900
- [ ] 5. 💰 Terraform Associate
- [ ] 6. 💰 CKA
- [ ] 7. 💰 Uptime Institute ATD ou AOS

> ⚠️ Preços, catálogos e disponibilidade de cursos e exames mudam com frequência. Confira sempre no site oficial antes de investir.

---

## 🔁 Revisão mensal

- [ ] O que concluí este mês?
- [ ] O que atrasou e por quê?
- [ ] Preciso trocar algum curso ou recurso?
- [ ] Atualizei o repositório e as anotações?
- [ ] Defini as metas do próximo mês?