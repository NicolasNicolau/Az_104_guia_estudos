# AZ-104 – Microsoft Azure Administrator

Guia de estudo aprofundado para a certificação **AZ-104**, com foco em cada domínio da prova, incluindo percentuais de incidência, resumos teóricos, serviços usados e links oficiais da Microsoft Learn.

---

## 🧭 Índice

1. Administração de Identidade (15–20%)  
2. Administração de Contas de Usuário e de Grupo (incluído em Identidade – 15–20%)  
3. Administração dos Recursos do Azure (15–20%)  
4. Administração de Rede Virtual (20–25%)  
5. Administração de Conectividade entre Sites (20–25%)  
6. Administração do Tráfego de Rede (20–25%)  
7. Administração do Armazenamento do Azure (10–15%)  
8. Administração de Máquinas Virtuais do Azure (25–30%)

---

### 1. Administração de Identidade (15–20%)

**Inclui:** Microsoft Entra ID (Azure AD), sincronização com AD local, Conditional Access, MFA, identidade híbrida.

**Para a prova:**  
- **Configurar sincronização com AD Connect**  
  ✅ Azure AD Connect permite sincronizar identidades locais (Active Directory) com o Microsoft Entra ID (Azure AD).  
  📍 **Onde acessar no portal:** Este recurso é configurado localmente, mas os usuários sincronizados podem ser visualizados em *Microsoft Entra ID > Usuários*.  
  ⚙️ **Como configurar:**  
    1. Baixe o instalador em: [https://aka.ms/aadconnect](https://aka.ms/aadconnect)  
    2. Execute no servidor AD local.  
    3. Escolha "Express Settings" ou "Custom".  
    4. Vincule ao tenant do Azure e defina filtros/sincronização.  
  🔗 [Guia oficial](https://learn.microsoft.com/pt-br/azure/active-directory/hybrid/how-to-connect-install-custom)

- **Implantar MFA (Autenticação Multifator) e Conditional Access**  
  ✅ MFA aumenta a segurança exigindo um segundo fator de autenticação, enquanto o Acesso Condicional aplica políticas de controle baseadas em condições.  
  📍 **Onde acessar no portal:** *Microsoft Entra ID > Segurança > Acesso condicional*.  
  ⚙️ **Como configurar:**  
    1. Para MFA, acesse *Microsoft Entra ID > Usuários > Configurações de MFA*.  
    2. Para Acesso Condicional, crie uma nova política definindo usuários, condições e controles.  
    3. Exemplo: exigir MFA para login externo ou de dispositivos não gerenciados.  
  🔗 [Configurar MFA](https://learn.microsoft.com/pt-br/azure/active-directory/authentication/tutorial-enable-azure-mfa)  
  🔗 [Acesso Condicional](https://learn.microsoft.com/pt-br/azure/active-directory/conditional-access/overview)

- **Compreender papéis administrativos**  
  ✅ Papéis administrativos definem permissões para gerenciar o tenant do Microsoft Entra ID.  
  📍 **Onde acessar no portal:** *Microsoft Entra ID > Papéis e administradores*.  
  ⚙️ **Como funciona:**  
    - Exemplo: Administrador Global tem acesso total; Administrador de Usuários gerencia contas e grupos.  
    - Você pode atribuir papéis a usuários/grupos diretamente no portal.  
  🔗 [Papéis do Azure AD](https://learn.microsoft.com/pt-br/azure/active-directory/roles/permissions-reference)

📚 [Microsoft Learn: Gerenciar identidades e governança](https://learn.microsoft.com/pt-br/training/paths/az-104-manage-identities-governance/)

---

### 2. Administração de Contas de Usuário e de Grupo (15–20%)

**Inclui:** criação, gerenciamento, acesso self-service, RBAC e controle de convidados.

**Para a prova:**  
- **Delegar permissões com RBAC (Role-Based Access Control)**  
  ✅ RBAC permite conceder acesso a recursos do Azure com base em funções atribuídas a usuários, grupos ou identidades gerenciadas.  
  📍 **Onde acessar no portal:** No recurso desejado, vá em *Controle de acesso (IAM)*.  
  ⚙️ **Como configurar:**  
    1. Acesse um recurso (ex: grupo de recursos).  
    2. Clique em *Controle de acesso (IAM)* > *Adicionar atribuição de função*.  
    3. Escolha a função (ex: Leitor, Colaborador) e selecione o usuário/grupo.  
  🔗 [Guia RBAC](https://learn.microsoft.com/pt-br/azure/role-based-access-control/overview)

- **Implementar SSPR (Self-Service Password Reset)**  
  ✅ Permite que usuários redefinam suas senhas sem intervenção do suporte técnico.  
  📍 **Onde acessar no portal:** *Microsoft Entra ID > Senhas > Redefinição de senha*.  
  ⚙️ **Como configurar:**  
    1. Habilite SSPR para todos os usuários ou grupos específicos.  
    2. Defina os métodos de autenticação exigidos (SMS, e-mail, app etc.).  
    3. Teste a funcionalidade com uma conta de usuário.  
  🔗 [Configurar SSPR](https://learn.microsoft.com/pt-br/azure/active-directory/authentication/tutorial-enable-sspr)

- **Configurar políticas de acesso de usuários externos (B2B)**  
  ✅ Define como convidados de outros domínios acessam recursos na sua organização via colaboração B2B.  
  📍 **Onde acessar no portal:** *Microsoft Entra ID > Configurações de usuários > Colaboração externa*.  
  ⚙️ **Como configurar:**  
    1. Ajuste configurações como permitir convidar, uso de MFA para convidados, etc.  
    2. Use grupos e RBAC para controlar permissões de convidados.  
  🔗 [Acesso de convidados (B2B)](https://learn.microsoft.com/pt-br/azure/active-directory/external-identities/what-is-b2b)

📚 [Microsoft Learn: Gerenciar identidades](https://learn.microsoft.com/pt-br/training/modules/manage-azure-identities/)

---

### 3. Administração dos Recursos do Azure (15–20%)

**Inclui:** Resource Groups, tags, locks, Azure Policy, Management Groups, controle de custos.

**Para a prova:**  
- **Aplicar Azure Policy**  
  ✅ Azure Policy permite definir regras que impõem conformidade sobre recursos (por exemplo: só criar VMs em regiões permitidas).  
  📍 **Onde acessar no portal:** *Pesquisar por "Política" no portal > Definições > Atribuições*.  
  ⚙️ **Como configurar:**  
    1. Acesse *Política (Policy)* no portal.  
    2. Vá em *Atribuições > Atribuir política*.  
    3. Escolha o escopo (assinatura, grupo de recursos), selecione a política e aplique.  
  🔗 [Guia Azure Policy](https://learn.microsoft.com/pt-br/azure/governance/policy/overview)

- **Configurar locks (ReadOnly/Delete)**  
  ✅ Os locks evitam alterações ou exclusões acidentais em recursos críticos.  
  📍 **Onde acessar no portal:** Em qualquer recurso ou grupo de recursos > *Bloqueios*.  
  ⚙️ **Como configurar:**  
    1. Vá até o recurso desejado.  
    2. Clique em *Bloqueios > Adicionar*.  
    3. Escolha entre `ReadOnly` (somente leitura) ou `Delete` (evita exclusão).  
  🔗 [Gerenciar Locks](https://learn.microsoft.com/pt-br/azure/azure-resource-manager/management/lock-resources)

- **Monitorar e controlar custos com Cost Management**  
  ✅ Ferramenta para análise de custos e previsão de gastos no Azure.  
  📍 **Onde acessar no portal:** *Cost Management + Billing > Custos e uso*.  
  ⚙️ **Como usar:**  
    1. Veja os gastos por serviço, grupo de recursos ou tags.  
    2. Configure alertas de orçamento.  
    3. Exporte relatórios ou conecte ao Power BI.  
  🔗 [Cost Management](https://learn.microsoft.com/pt-br/azure/cost-management-billing/cost-management-billing-overview)

📚 [Microsoft Learn: Identidades e governança](https://learn.microsoft.com/pt-br/training/paths/az-104-manage-identities-governance/)

---

### 4. Administração de Rede Virtual (20–25%)

**Inclui:** criação de VNets/subnets, IPs públicos e privados, DNS personalizado, NSG, VNet Peering, rotas.

**Para a prova:**  
- **Criar e configurar VNets, subnets e peering**  
  ✅ VNets permitem isolar redes virtuais no Azure. Subnets segmentam essas redes. Peering conecta VNets entre si.  
  📍 **Onde acessar no portal:** *Rede Virtual > Criar > VNet*.  
  ⚙️ **Como configurar:**  
    1. Crie uma VNet com nome, região e faixa de IP.  
    2. Adicione sub-redes conforme necessidade (ex: front-end, DB).  
    3. Para peering, vá em *Peerings > Adicionar* e configure permissões.  
  🔗 [Criar VNets e peering](https://learn.microsoft.com/pt-br/azure/virtual-network/virtual-networks-overview)

- **Implantar NSGs e verificar regras efetivas**  
  ✅ NSGs controlam o tráfego de rede para subnets e NICs, com regras de entrada e saída.  
  📍 **Onde acessar no portal:** *Grupos de segurança de rede (NSG)*.  
  ⚙️ **Como configurar:**  
    1. Crie um NSG e adicione regras (por porta, IP, protocolo).  
    2. Associe o NSG a uma subnet ou NIC.  
    3. Use o recurso de “regras efetivas” para ver o que está aplicado.  
  🔗 [Guia NSG](https://learn.microsoft.com/pt-br/azure/virtual-network/network-security-groups-overview)

- **Resolver DNS via zonas públicas e privadas**  
  ✅ DNS no Azure pode usar zonas públicas (acessíveis via internet) ou privadas (internas à rede).  
  📍 **Onde acessar no portal:** *DNS Zones > Adicionar*.  
  ⚙️ **Como configurar:**  
    1. Crie uma zona DNS pública (ex: contoso.com) ou privada para rede interna.  
    2. Crie registros (A, CNAME, MX etc.).  
    3. Associe zonas privadas a VNets para resolução interna.  
  🔗 [DNS no Azure](https://learn.microsoft.com/pt-br/azure/dns/dns-overview)

📚 [Microsoft Learn: Redes Virtuais](https://learn.microsoft.com/pt-br/training/paths/az-104-manage-virtual-networks/)

---

### 5. Administração de Conectividade entre Sites (20–25%)

**Inclui:** VPN Gateway, ExpressRoute, Virtual WAN, Bastion.

**Para a prova:**  
- **Criar conexões VPN S2S e P2S**  
  ✅ Permite conectar redes locais ou dispositivos remotos ao Azure por meio de VPN.  
  📍 **Onde acessar no portal:** *Pesquisar por “VPN Gateway” > Criar gateway de rede virtual*.  
  ⚙️ **Como configurar:**  
    1. Crie uma VNet e um Gateway Subnet.  
    2. Crie o recurso *VPN Gateway*.  
    3. Configure conexões Site-to-Site (com IP público e roteador) ou Point-to-Site (usuários remotos com certificado).  
  🔗 [Configurar VPN Gateway](https://learn.microsoft.com/pt-br/azure/vpn-gateway/vpn-gateway-about-vpngateways)

- **Configurar ExpressRoute**  
  ✅ Conexão dedicada e privada entre a infraestrutura local e o Azure (alta largura e baixa latência).  
  📍 **Onde acessar no portal:** *Pesquisar por “ExpressRoute” > Criar circuito*.  
  ⚙️ **Como configurar:**  
    1. Solicite o circuito ExpressRoute no portal.  
    2. Forneça à operadora o *Service Key* gerado.  
    3. Após provisionamento, configure a conexão com sua VNet.  
  🔗 [ExpressRoute Overview](https://learn.microsoft.com/pt-br/azure/expressroute/expressroute-introduction)

- **Acessar com segurança via Azure Bastion**  
  ✅ Permite acesso RDP/SSH a VMs diretamente pelo portal, sem IP público.  
  📍 **Onde acessar no portal:** *Rede > Bastion Hosts*.  
  ⚙️ **Como configurar:**  
    1. Crie um host Bastion em uma VNet com subnet `AzureBastionSubnet`.  
    2. Após provisionado, use o botão “Conectar” na VM com Bastion como método.  
  🔗 [Azure Bastion](https://learn.microsoft.com/pt-br/azure/bastion/bastion-overview)

📚 [Microsoft Learn: Conectividade entre redes virtuais](https://learn.microsoft.com/pt-br/training/modules/configure-connectivity-between-azure-virtual-networks/)

---

### 6. Administração do Tráfego de Rede (20–25%)

**Inclui:** Load Balancer, Application Gateway, Azure Firewall, Network Watcher.

**Para a prova:**  
- **Configurar Load Balancer (inbound/outbound rules)**  
  ✅ Distribui automaticamente o tráfego entre várias VMs. Pode ser público (internet) ou interno.  
  📍 **Onde acessar no portal:** *Balanceador de carga > Criar*.  
  ⚙️ **Como configurar:**  
    1. Crie um Load Balancer (escolha público ou interno).  
    2. Adicione backend pool (VMs).  
    3. Configure health probes e regras de balanceamento (porta/protocolo).  
  🔗 [Load Balancer Overview](https://learn.microsoft.com/pt-br/azure/load-balancer/load-balancer-overview)

- **Implementar Application Gateway + WAF**  
  ✅ Application Gateway distribui tráfego HTTP/HTTPS com base em regras avançadas (Layer 7). WAF protege contra ameaças da web (OWASP).  
  📍 **Onde acessar no portal:** *Pesquisar por “Application Gateway” > Criar*.  
  ⚙️ **Como configurar:**  
    1. Crie um Application Gateway com listener HTTPS.  
    2. Defina regras de roteamento (URL path, header etc.).  
    3. Habilite WAF no modo Detection ou Prevention.  
  🔗 [Application Gateway com WAF](https://learn.microsoft.com/pt-br/azure/web-application-firewall/ag/ag-overview)

- **Monitorar conectividade com Network Watcher**  
  ✅ Ferramenta para diagnosticar e monitorar conexões de rede, pacotes, NSG, VPN, etc.  
  📍 **Onde acessar no portal:** *Network Watcher > Iniciar Diagnóstico*.  
  ⚙️ **Como usar:**  
    1. Habilite o Network Watcher na região.  
    2. Use ferramentas como “IP Flow Verify”, “Connection Troubleshoot” e “NSG Diagnostics”.  
  🔗 [Network Watcher Overview](https://learn.microsoft.com/pt-br/azure/network-watcher/network-watcher-monitoring-overview)

📚 [Microsoft Learn: Balanceamento de carga no Azure](https://learn.microsoft.com/pt-br/training/modules/configure-load-balancing-azure/)

---

### 7. Administração do Armazenamento do Azure (10–15%)

**Inclui:** Blobs, Files, containers, tiers, replicação, SAS, File Sync, AzCopy.

**Para a prova:**  
- **Criar Storage Accounts e configurar replicações**  
  ✅ Uma Storage Account armazena objetos como blobs, arquivos, filas e tabelas.  
  📍 **Onde acessar no portal:** *Armazenamento > Criar conta de armazenamento*.  
  ⚙️ **Como configurar:**  
    1. Escolha nome, região e tipo de redundância (LRS, GRS, ZRS etc.).  
    2. Selecione tipo de desempenho (Standard ou Premium).  
    3. Após criar, gerencie containers, arquivos, permissões etc.  
  🔗 [Criar Storage Account](https://learn.microsoft.com/pt-br/azure/storage/common/storage-account-create)

- **Definir políticas de ciclo de vida**  
  ✅ Automatiza a movimentação ou exclusão de blobs com base em regras (ex: mover para tier de arquivamento após 30 dias).  
  📍 **Onde acessar no portal:** Dentro da Storage Account > *Gerenciamento de dados > Regras de ciclo de vida*.  
  ⚙️ **Como configurar:**  
    1. Crie uma nova regra.  
    2. Defina filtros (prefixo, tipo de blob).  
    3. Adicione ações como mover para tier mais frio ou deletar após X dias.  
  🔗 [Lifecycle Management](https://learn.microsoft.com/pt-br/azure/storage/blobs/lifecycle-management-policy-configure)

- **Gerenciar SAS e permissões**  
  ✅ Shared Access Signature (SAS) permite conceder acesso limitado e com tempo definido a objetos da conta.  
  📍 **Onde acessar no portal:** Storage Account > *Chaves de acesso compartilhado (SAS)*.  
  ⚙️ **Como configurar:**  
    1. Escolha serviços, permissões e duração.  
    2. Gere a URL SAS.  
    3. Distribua com segurança aos usuários que precisam de acesso.  
  🔗 [Guia SAS](https://learn.microsoft.com/pt-br/azure/storage/common/storage-sas-overview)

📚 [Microsoft Learn: Implementar e gerenciar armazenamento](https://learn.microsoft.com/pt-br/training/paths/az-104-implement-manage-storage/)

---

### 8. Administração de Máquinas Virtuais do Azure (25–30%)

**Inclui:** criação e gerenciamento de VMs, discos, extensões, scale sets, disponibilidade, backup.

**Para a prova:**  
- **Criar e escalar VMs via Portal, CLI e ARM**  
  ✅ As VMs são a base da computação no Azure. Podem ser criadas manualmente ou por automação.  
  📍 **Onde acessar no portal:** *Máquinas Virtuais > Criar VM*.  
  ⚙️ **Como criar:**  
    1. Defina nome, região, SO, tamanho, rede e disco.  
    2. Use Azure CLI (`az vm create`) ou templates ARM para automação.  
  🔗 [Criar VM](https://learn.microsoft.com/pt-br/azure/virtual-machines/windows/quick-create-portal)

- **Implantar scale sets e disponibilidade (zones/sets)**  
  ✅ VM Scale Sets gerenciam várias VMs idênticas com escalabilidade automática. Zonas de disponibilidade garantem alta disponibilidade.  
  📍 **Onde acessar no portal:** *Scale Sets* ou ao criar uma VM (aba de alta disponibilidade).  
  ⚙️ **Como configurar:**  
    1. Para alta disponibilidade, selecione Zonas (multi-AZ) ou Conjuntos de disponibilidade.  
    2. Para scale sets, use o assistente e configure mínimo, máximo e regras de escalabilidade.  
  🔗 [Scale Sets](https://learn.microsoft.com/pt-br/azure/virtual-machine-scale-sets/overview)

- **Usar extensões e configurar Azure Backup**  
  ✅ Extensões são scripts e ferramentas que rodam após o provisionamento da VM. Backup protege contra perda de dados.  
  📍 **Onde acessar no portal:** VM > *Extensões* e *Backup*.  
  ⚙️ **Como usar:**  
    1. Adicione extensões como Custom Script, Antimalware, Diagnóstico.  
    2. Ative backup definindo cofre de serviços e política de retenção.  
  🔗 [Extensões de VM](https://learn.microsoft.com/pt-br/azure/virtual-machines/extensions/overview)  
  🔗 [Backup de VM](https://learn.microsoft.com/pt-br/azure/backup/backup-azure-arm-vms-introduction)

📚 [Microsoft Learn: Implantar e gerenciar computação no Azure](https://learn.microsoft.com/pt-br/training/paths/az-104-implement-deploy-compute/)

## 📊 Distribuição de Conteúdo na Prova

| Área                                   | Incidência estimada |
|----------------------------------------|----------------------|
| Identidade e Governança                | 15–20%               |
| Recursos do Azure                      | 15–20%               |
| Redes Virtuais & Conectividade         | 20–25%               |
| Tráfego de Rede                        | 20–25%               |
| Armazenamento                          | 10–15%               |
| Máquinas Virtuais                      | 25–30%               |

Fonte: [Microsoft Skills Outline AZ-104 (oficial)](https://learn.microsoft.com/certifications/resources/study-guides/az-104)

---

## 🧠 Dicas de Estudo

- Estude por prioridade: **VMs, Redes e Identidade** são os mais cobrados.  
- Use os **sandboxes do Microsoft Learn** para praticar gratuitamente.  
- Faça provas simuladas e revise erros com atenção.  
- Crie flashcards com conceitos como: replicação de storage, tipos de disco, políticas, RBAC.  
- Pratique o uso de **Azure CLI, PowerShell e portal**.

---

# 📘 Sumário de Siglas por Tema – AZ-104

Este glossário organiza as siglas por categoria temática, com suas traduções e explicações.

## 🔹 Identidade e Acesso

### SSPR – Self-Service Password Reset (Redefinição de Senha Self-Service)
Permite que usuários redefinam suas próprias senhas sem suporte, com métodos como SMS ou e-mail.

### RBAC – Role-Based Access Control (Controle de Acesso Baseado em Função)
Controle de acesso que define permissões por função atribuída a usuários ou grupos.

### MFA – Multi-Factor Authentication (Autenticação Multifator)
Requer dois ou mais métodos para autenticação segura.

### AADJ – Azure AD Join (Ingressar no Azure AD)
Vincula dispositivos diretamente ao Azure AD.

### AADDS – Azure Active Directory Domain Services (Serviços de Domínio do Azure AD)
Permite usar domínios compatíveis com AD sem precisar de servidores de domínio locais.

### B2B – Business-to-Business (Negócio para Negócio)
Permite colaboração com usuários externos ao seu tenant Azure AD.

## 🔹 Rede e Segurança

### NSG – Network Security Group (Grupo de Segurança de Rede)
Firewall de nível de rede para controlar tráfego de entrada e saída em subnets ou NICs.

### VNet – Virtual Network (Rede Virtual)
Rede virtual no Azure que permite isolamento e segmentação de recursos.

### NIC – Network Interface Card (Placa de Interface de Rede)
Dispositivo de rede que conecta uma VM à VNet.

### DNS – Domain Name System (Sistema de Nomes de Domínio)
Resolve nomes para endereços IP, usado em redes públicas e privadas.

### BGP – Border Gateway Protocol (Protocolo de Fronteira)
Usado para roteamento dinâmico entre redes no Azure.

### WAF – Web Application Firewall (Firewall de Aplicações Web)
Protege contra ataques como SQL injection e XSS.

## 🔹 Armazenamento

### SAS – Shared Access Signature (Assinatura de Acesso Compartilhado)
Permite gerar links com acesso temporário e controlado a recursos de armazenamento no Azure.

### GRS – Geo-Redundant Storage (Armazenamento com Redundância Geográfica)
Replica dados para outra região para alta disponibilidade.

### LRS – Locally Redundant Storage (Armazenamento com Redundância Local)
Mantém 3 cópias dos dados na mesma região.

### ZRS – Zone-Redundant Storage (Armazenamento com Redundância entre Zonas)
Replica dados entre zonas de disponibilidade.

### VHD – Virtual Hard Disk (Disco Rígido Virtual)
Formato usado por discos de máquinas virtuais no Azure.

## 🔹 Máquinas Virtuais e Computação

### VM – Virtual Machine (Máquina Virtual)
Recurso de computação com sistema operacional próprio no Azure.

### VMSS – Virtual Machine Scale Set (Conjunto de Escalonamento de Máquinas Virtuais)
Conjunto de VMs idênticas com escalabilidade automática, ideal para cargas variáveis.

### BYOL – Bring Your Own License (Traga Sua Própria Licença)
Permite usar licenças existentes (Windows, SQL) em VMs no Azure.

## 🔹 Automação e Gerenciamento

### CLI – Command-Line Interface (Interface de Linha de Comando)
Ferramenta usada para automatizar operações no Azure via terminal.

### ARM – Azure Resource Manager (Gerenciador de Recursos do Azure)
Modelo de implantação baseado em template JSON no Azure.

### JSON – JavaScript Object Notation (Notação de Objetos JavaScript)
Formato de dados leve usado em APIs e templates.

## 🔹 Backup e Recuperação

### RPO/RTO – Recovery Point Objective / Recovery Time Objective (Objetivo de Ponto/Tempo de Recuperação)
Limites de tolerância à perda de dados e tempo necessário para restaurar serviços.

## 🔹 Diretório e Autenticação

### AD – Active Directory (Diretório Ativo)
Serviço de diretório local (on-premises) que pode ser sincronizado com o Azure AD.
