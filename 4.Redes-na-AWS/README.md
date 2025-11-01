# 🌐 Módulo 4 — Redes na AWS

## 📘 Conteúdo do Módulo

1. **Amazon VPC (Virtual Private Cloud)**
2. **Amazon Subnet**
3. **Amazon Security Group**
4. **Amazon Route 53**
5. **Amazon CloudFront**
6. **Amazon Elastic Load Balancer (ELB)**

---

## 🧭 Amazon VPC — Rede Virtual Privada

O **Amazon VPC (Virtual Private Cloud)** é o serviço que permite criar uma **rede virtual isolada dentro da AWS**, onde você pode provisionar recursos com total controle sobre IPs, segurança e conectividade.

### 🔹 Características Principais

- **Isolamento de rede:** fornece um ambiente seguro e dedicado para seus recursos.
- **Controle de tráfego:** usa **Security Groups** e **Network ACLs** para gerenciar entrada (inbound) e saída (outbound).
- **Sub-redes públicas e privadas:** permite dividir sua rede em segmentos com diferentes níveis de acesso.
- **Controle de endereçamento IP:** você define seu próprio intervalo de IPs.
- **Conectividade híbrida:** integração com redes locais via **VPN** ou **AWS Direct Connect**.

### 🔹 Tipos de Serviços

- **Serviços Públicos:** não requerem VPC (ex: S3, CloudFront).
- **Serviços Privados:** precisam de VPC configurada (ex: EC2, RDS, Lambda privado).

🔗 [Documentação AWS VPC](https://docs.aws.amazon.com/pt_br/vpc/latest/userguide/vpc-example-private-subnets-nat.html)

---

## 🧩 Amazon Subnet — Sub-redes na Nuvem

Uma **Subnet (Sub-rede)** é um intervalo de endereços IP dentro da VPC.  
Você pode criar sub-redes específicas para diferentes tipos de recursos, como servidores de aplicação, bancos de dados ou serviços públicos.

### 🔹 Estrutura e Função

- Cada **sub-rede** deve estar **inteiramente dentro de uma Zona de Disponibilidade (AZ)**.
- Recursos como **instâncias EC2** são criados dentro das sub-redes.
- **Security Groups** e **Network ACLs** controlam o tráfego de rede dentro e fora da sub-rede.

### 🔹 Tipos de Sub-redes

| Tipo        | Descrição                                                               |
| ----------- | ----------------------------------------------------------------------- |
| **Pública** | Conectada à internet por meio de um **Internet Gateway**                |
| **Privada** | Restrita à rede interna, usada para bancos de dados e serviços internos |

---

## 🔒 Amazon Security Group — Controle de Acesso

O **Amazon Security Group (SG)** atua como um **firewall virtual**, controlando o tráfego de entrada e saída de suas instâncias e recursos dentro da VPC.

### 🔹 Funções Principais

- Define **regras de acesso** baseadas em **portas, protocolos e endereços IP**.
- Controla **acessos via SSH (porta 22)** e **RDP (porta 3389)**, entre outros.
- Pode ser associado a uma ou mais instâncias EC2.
- Trabalha em conjunto com **Network ACLs** para reforçar a segurança.

💡 **Exemplo:**  
Permitir acesso SSH apenas do IP corporativo e negar todas as outras origens.

---

## 🌍 Amazon Route 53 — Gerenciamento de DNS

O **Amazon Route 53** é o serviço de **DNS (Domain Name System)** da AWS.  
Ele traduz nomes de domínio legíveis (ex: `www.exemplo.com`) para endereços IP.

### 🔹 Principais Recursos

- **Resolução de DNS:** converte nomes de domínio em endereços IP internos ou públicos.
- **Roteamento de tráfego:** distribui solicitações para regiões ou instâncias específicas.
- **Alta disponibilidade:** integração com **Health Checks** para detectar falhas.
- **Integração com VPCs:** resolução interna de nomes privados na AWS.

---

## ⚡ Amazon CloudFront — Entrega Global de Conteúdo (CDN)

O **Amazon CloudFront** é o serviço de **Content Delivery Network (CDN)** da AWS.  
Ele distribui conteúdo (imagens, vídeos, sites, APIs) para usuários em **baixa latência** e **alta velocidade**.

### 🔹 Características

- **Distribuição global** por meio de **Edge Locations**.
- **Redução de latência** e melhora na experiência do usuário.
- **Cache inteligente:** armazena conteúdo próximo ao usuário final.
- **Integração com S3, EC2, ELB e Route 53.**

### 🔹 Benefícios

- Melhor desempenho e disponibilidade global.
- Redução do tráfego direto nos servidores de origem.
- Segurança com **HTTPS, WAF e TLS** integrados.

---

## ⚖️ Amazon Elastic Load Balancer (ELB) — Balanceamento de Carga

O **Elastic Load Balancer (ELB)** distribui automaticamente o tráfego de rede entre vários servidores para aumentar a **disponibilidade** e o **desempenho** das aplicações.

### 🔹 Funções

- **Escalabilidade automática:** ajusta a carga conforme o volume de tráfego.
- **Alta disponibilidade:** redireciona tráfego automaticamente em caso de falhas.
- **Monitoramento integrado:** com métricas no **Amazon CloudWatch**.

### 🔹 Tipos de Load Balancers

| Tipo                                | Descrição                                                      | Uso Ideal                                      |
| ----------------------------------- | -------------------------------------------------------------- | ---------------------------------------------- |
| **Application Load Balancer (ALB)** | Gerencia tráfego HTTP/HTTPS com regras avançadas de roteamento | Aplicações web modernas, APIs REST, WebSockets |
| **Network Load Balancer (NLB)**     | Gerencia tráfego TCP/UDP com alta performance e baixa latência | Jogos online, sistemas financeiros, IoT        |
| **Gateway Load Balancer (GWLB)**    | Combina balanceamento com segurança de rede (firewall, IDS)    | Ambientes com múltiplas camadas de segurança   |
| **Classic Load Balancer (CLB)**     | Versão legada para tráfego básico HTTP/TCP                     | Aplicações mais antigas                        |

### 🔹 Aplicações Práticas

- Melhorar **escalabilidade** e **resiliência** de sistemas híbridos (nuvem + local).
- Equilibrar o tráfego entre instâncias em diferentes **zonas de disponibilidade**.
- Trabalhar em conjunto com **Auto Scaling** e **Route 53** para redundância.
