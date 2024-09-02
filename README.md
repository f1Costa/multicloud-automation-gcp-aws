## README.md

# Projeto: Automação Multicloud com AWS e GCP

## Descrição

Este projeto visa automatizar a criação e gestão de credenciais AWS e GCP, além de configurar e gerenciar recursos na nuvem utilizando scripts Bash e Terraform. A solução abrange desde a criação e backup de arquivos de credenciais até a orquestração de infraestrutura multicloud, permitindo uma integração fluida entre os ambientes AWS e GCP.

## Funcionalidades

- **Criação de Chaves de Acesso AWS:** Geração de um arquivo `accessKeys.csv` contendo as chaves de acesso e secretas da AWS.
- **Configuração de Projetos GCP:** Atualização de arquivos de configuração com o ID do projeto GCP.
- **Backup e Gestão de Credenciais:** Criação de backups dos arquivos de credenciais AWS e GCP antes de qualquer modificação.
- **Inicialização de Arquivos de Configuração:** Criação e inicialização dos arquivos `credentials_multiclouddeploy` e `terraform.tfvars`.
- **Configuração de Infraestrutura:** Provisionamento de recursos na AWS e GCP utilizando Terraform.

## Estrutura do Projeto

- **scripts/**: Contém os scripts Bash para criar e gerenciar credenciais AWS e GCP.
- **terraform/**: Diretório destinado aos arquivos de configuração Terraform para AWS e GCP.

## Pré-requisitos

- **AWS CLI:** Necessário para operações relacionadas às credenciais AWS.
- **GCP SDK:** Necessário para operações relacionadas ao GCP, como a obtenção do ID do projeto.
- **Terraform:** Ferramenta de IaC para gerenciar a infraestrutura em múltiplas nuvens.
- **Bash:** Ambiente de shell necessário para a execução dos scripts.

## Uso

### Criação de Chaves de Acesso AWS

1. **Gerar Chaves AWS:**
   ```bash
   ./script.sh <aws_access_key_id> <aws_secret_access_key>
   ```
   Isso criará um arquivo `key.csv` com as chaves fornecidas.

2. **Executar o Script Principal para AWS:**
   ```bash
   ./script.sh <path_to_accessKeys.csv>
   ```
   Crie as credenciais AWS e configure o Terraform.

### Configuração de Projeto GCP

1. **Adicionar Projeto GCP:**
   ```bash
   ./gcp_script.sh <GCP_project_id>
   ```
   Atualize os arquivos de configuração do Deployment Manager e Terraform com o ID do projeto GCP.

### Provisionamento de Recursos

1. **Configurar Infraestrutura com Terraform:**
   Após executar os scripts de configuração, navegue até o diretório `terraform` e execute os comandos Terraform habituais:
   ```bash
   terraform init
   terraform apply
   ```

## Configuração Terraform

O projeto inclui configurações Terraform para criar e gerenciar recursos na AWS e GCP:

- **AWS:** Provisionamento de um bucket S3.
- **GCP:** Configuração de uma VPC, sub-rede, conexão de rede privada, instância de banco de dados Cloud SQL, e cluster Kubernetes (GKE).

## Considerações Finais

Este projeto oferece uma solução integrada para gerenciar credenciais e infraestrutura em ambientes multicloud, utilizando automação via Bash e IaC com Terraform. Ele pode ser adaptado para se adequar a diferentes necessidades e configurações específicas.