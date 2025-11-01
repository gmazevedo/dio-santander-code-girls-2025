# 💾 Módulo 6 — Serviços de Armazenamento e CDN

## 📘 Conteúdo do Módulo

1. **Amazon S3 – Simple Storage Service**
2. **Amazon Glacier – Armazenamento de Longo Prazo**
3. **Amazon CloudFront – Rede de Distribuição de Conteúdo (CDN)**

---

## 🗄️ Amazon S3 — Armazenamento de Objetos na Nuvem

O **Amazon S3 (Simple Storage Service)** é o serviço de **armazenamento de objetos** da AWS, projetado para armazenar, organizar e recuperar grandes volumes de dados de forma **segura, durável e escalável**.

### 🔹 Características Principais

- **Armazenamento de Objetos:**  
  Cada arquivo é um _objeto_, armazenado em um _bucket_ (contêiner).  
  Cada bucket tem um **nome globalmente único**.
- **Classes de Armazenamento:**
  - **S3 Standard:** acesso frequente com alta disponibilidade.
  - **S3 Intelligent-Tiering:** muda automaticamente os objetos entre classes conforme o uso.
  - **S3 Glacier / Glacier Deep Archive:** para armazenamento de longo prazo e baixo custo.
- **Durabilidade e Disponibilidade:**
  - Durabilidade de **99,999999999% (11 noves)**.
  - Disponibilidade de **99,99%**.
- **Segurança:**
  - Criptografia em repouso e em trânsito.
  - Controle de acesso com **IAM Policies**, **ACLs** e **Bucket Policies**.

### 🔹 Políticas de Acesso

Permitem restringir quem pode visualizar ou modificar objetos nos buckets.  
As políticas são definidas em formato **JSON**, com chaves e valores que controlam permissões.

Exemplo de **Bucket Policy Pública**:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::SEU_BUCKET/*"
    }
  ]
}
```

### 🔹 Aplicações

- Armazenamento de sites estáticos.
- Backups e logs de sistemas.
- Repositório para aplicações web e móveis.
- Integração com serviços como CloudFront e Lambda.

## 🧊 Amazon Glacier — Armazenamento de Longo Prazo

O Amazon S3 Glacier é uma classe de armazenamento de arquivamento voltada para dados raramente acessados, reduzindo custos de forma significativa.

### 🔹 Características

- Armazenamento durável e de baixo custo.
- Ideal para dados que serão acessados após 5 dias ou mais.
- Integrado ao S3 Lifecycle Management, permitindo migração automática de dados antigos para o Glacier.
- Projetado para arquivamento de:
  - Dados científicos.
  - Documentos de saúde.
  - Registros de conformidade e auditoria.

### 🔹 Prazos e Custos

| Tipo                        | Tempo de Recuperação | Duração Mínima | Custo Aproximado |
| --------------------------- | -------------------- | -------------- | ---------------- |
| **S3 Glacier**              | 3 a 5 horas          | 90 dias        | US$ 0,01/GB      |
| **S3 Glacier Deep Archive** | até 12 horas         | 180 dias       | US$ 0,005/GB     |

### 🔹 Casos de Uso

- Backups de longo prazo.
- Arquivamento histórico de empresas e órgãos públicos.
- Armazenamento regulatório e científico.

## 🚛 AWS Snow Family — Transferência em Larga Escala

Quando há necessidade de migrar grandes volumes de dados (terabytes a petabytes), utiliza-se a AWS Snow Family.

### 🔹 Serviços

| Serviço               | Capacidade        | Descrição                                                              |
| --------------------- | ----------------- | ---------------------------------------------------------------------- |
| **AWS Snowball**      | Até 80 TB         | Dispositivo físico usado para importar/exportar dados de forma segura. |
| **AWS Snowball Edge** | Até 100 TB        | Oferece **computação local + transferência rápida** de dados.          |
| **AWS Snowmobile**    | Até 100 Petabytes | Caminhão projetado para migração em escala extrema para a AWS.         |

Esses dispositivos são criptografados, rastreáveis e usados em regiões com conectividade limitada à internet.

🔗 [AWS Snow Family](https://aws.amazon.com/pt/snowball/)

## 🌎 Amazon CloudFront — Rede de Entrega de Conteúdo (CDN)

O Amazon CloudFront é o serviço de Content Delivery Network (CDN) da AWS, responsável por distribuir conteúdo globalmente com baixa latência e alta velocidade.

### 🔹 Funcionamento

- Faz cache de arquivos estáticos (imagens, vídeos, CSS, JS, etc.) em Edge Locations (POPs) próximos aos usuários.
- Quando um arquivo é solicitado:
  - Se já estiver no cache, é entregue imediatamente.
  - Caso contrário, é buscado do servidor de origem e armazenado localmente para os próximos acessos.

### 🔹 Benefícios

- Redução da latência e melhor desempenho de carregamento.
- Economia de largura de banda e menor carga nos servidores de origem.
- Integração nativa com S3, EC2 e Route 53.
- Segurança: suporte a HTTPS, autenticação e proteção contra ataques DDoS.

### 🔹 Exemplo Prático

Um e-commerce pode usar o CloudFront para distribuir imagens de produtos.
As imagens são entregues a partir do POP mais próximo, garantindo carregamento instantâneo para o usuário final.
