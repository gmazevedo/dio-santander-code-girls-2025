# ☁️ Módulo 2 — Computação na Nuvem com Amazon EC2

## 📘 Conteúdo do Módulo

1. **Amazon EC2 – Elastic Compute Cloud**  
2. **Amazon S3 – Simple Storage Service**  
3. **Amazon EBS – Elastic Block Store**  
4. **Gerenciamento e Otimização de Recursos EC2**

---

## ⚙️ Amazon EC2 — Elastic Compute Cloud

O **Amazon EC2 (Elastic Compute Cloud)** é o serviço de máquinas virtuais da AWS, que fornece capacidade computacional escalável sob demanda.  
Ele permite criar **instâncias** (VMs) com sistema operacional Windows ou Linux, escolhendo CPU, memória, armazenamento e rede conforme a necessidade.

### 🔹 Conceito
- Modelo **IaaS (Infraestrutura como Serviço)** — o usuário é responsável pelos aplicativos, dados e conexões.  
- Cada instância EC2 é composta por:
  - **CPU (vCPUs)**
  - **Memória RAM**
  - **Disco (EBS ou armazenamento temporário)**
  - **Rede e Sistema Operacional**

### 🔹 Configuração e Segurança
- As imagens de sistema são chamadas de **AMIs (Amazon Machine Images)**.  
- O acesso é controlado por **Security Groups**, que atuam como firewalls definindo portas, protocolos e IPs de origem.  
- Permite configuração de **chaves SSH**, **endereços elásticos (Elastic IPs)** e **balanceamento de carga**.

### 🔹 Escolha da Instância Correta
Selecionar a instância ideal é essencial para **equilibrar custo e desempenho**:
- Avalie o perfil da aplicação (CPU, memória, rede).  
- Use instâncias otimizadas para casos de uso específicos (ex: T3 para uso geral, C5 para computação intensiva, R5 para memória intensiva).

---

## 🗄️ Amazon S3 — Simple Storage Service

O **Amazon S3** é o serviço de armazenamento de objetos da AWS.  
Ideal para armazenar, organizar e recuperar grandes volumes de dados de forma segura, escalável e altamente disponível.

### 🔹 Características
- Armazenamento de dados em **“buckets”** (recipientes).  
- Objetos podem ser acessados via **URL** ou **integrações com outros serviços AWS**.  
- Permite configurar **controle de acesso (IAM Policies)** e **versionamento**.

### 🔹 Classes de Armazenamento
Cada classe oferece diferentes níveis de custo e disponibilidade:
- **S3 Standard:** alta disponibilidade e baixa latência.  
- **S3 Standard-IA (Infrequent Access):** menor custo para dados acessados esporadicamente.  
- **S3 Glacier / Deep Archive:** armazenamento de longo prazo com custo reduzido.  

### 🔹 Ciclo de Vida (Lifecycle)
Permite definir regras automáticas para:
- Mover objetos entre classes (ex: de Standard → Glacier).  
- Excluir objetos após um tempo definido.  
Isso garante eficiência de custos e gestão automatizada de dados.

---

## 💾 Amazon EBS — Elastic Block Store

O **Amazon EBS** fornece volumes de armazenamento em blocos altamente disponíveis e expansíveis para uso com instâncias EC2.

### 🔹 Conceito
- Funciona como um disco rígido virtual anexado à instância EC2.  
- Permite criar, expandir e remover volumes de forma dinâmica.  
- Pode ser utilizado para armazenar bancos de dados, arquivos de log e sistemas de arquivos.

### 🔹 Exemplos de Uso
- Armazenamento de dados de MySQL, PostgreSQL ou Oracle.  
- Logs de aplicações web e arquivos temporários.  
- Expansão rápida do disco sem necessidade de desligar a instância.

---

## ⚡ Otimização de Recursos na AWS

A otimização visa melhorar o desempenho e reduzir custos dos recursos em nuvem.

### 🔹 1. Desligar Instâncias Inativas
- Ambientes de teste, desenvolvimento e treinamento podem ser desligados fora do horário comercial.  
- Evita cobranças desnecessárias e melhora a eficiência financeira.

### 🔹 2. Remover Recursos Ociosos
- Recursos não utilizados continuam gerando custos.  
- Deve-se monitorar e excluir volumes, snapshots, IPs elásticos e instâncias inativas.

### 🔹 3. Escalabilidade
A escalabilidade permite ajustar os recursos conforme a demanda.

**Escalonamento Vertical:**  
- Aumenta ou reduz capacidade de uma instância (vCPUs, memória, storage).  
- Útil para lidar com picos temporários.

**Escalonamento Horizontal:**  
- Adiciona ou remove instâncias para balancear carga.  
- Exemplo: adicionar servidores durante o horário de pico.

---

## 💰 Tipos de Instâncias EC2 (Modelos de Compra)

| Tipo | Descrição | Vantagens | Desvantagens |
|------|------------|------------|---------------|
| **On-Demand** | Pagamento por hora/segundo de uso. | Flexibilidade total. | Custo mais alto em longo prazo. |
| **Reserved Instances** | Contrato anual ou trienal com desconto. | Economia significativa (até 75%). | Menor flexibilidade. |
| **Spot Instances** | Uso de capacidade ociosa com descontos de até 90%. | Muito baratas. | Podem ser encerradas pela AWS com 2 minutos de aviso. |
