🚀 Resumo Completo do Bootcamp: Microsoft AZ-900 Certification

## 📋 Visão Geral do Bootcamp
Este repositório documenta minha jornada completa através da Formação Microsoft AZ-900 Certification na DIO, abrangendo todos os conceitos fundamentais de computação em nuvem, serviços Azure, governança, segurança e ferramentas de gerenciamento.

## 🎯 O que Aprendi no Bootcamp

### **1. Fundamentos de Computação em Nuvem**
- **Modelos de Serviço**: IaaS, PaaS, SaaS - diferenças e casos de uso
- **Modelos de Implantação**: Pública, Privada, Híbrida e Community Cloud
- **Vantagens da Nuvem**: Economia de escala, elasticidade, pay-as-you-go
- **Conceitos Chave**: Alta disponibilidade, escalabilidade, tolerância a falhas

### **2. Serviços de Computação Azure**
#### **Máquinas Virtuais e Escalabilidade**
```
azurecli
# Criando VM com Azure CLI
az vm create \
  --name minha-vm \
  --resource-group meu-rg \
  --image UbuntuLTS \
  --size Standard_D2s_v3 \
  --admin-username azureuser \
  --generate-ssh-keys

  ```
  - **Tipos de VMs**: Séries B, D, F, E, NC - casos de uso específicos

- **Scale Sets**: Dimensionamento automático baseado em demanda

- **Availability Sets**: Alta disponibilidade entre domínios de falha/atualização

- **Azure Functions**: Computação serverless orientada a eventos

### **Contêineres e Kubernetes**
- **Azure Container Instances**: Contêineres sem orquestração

- **Azure Kubernetes Service (AKS)**: Orquestração de contêineres em escala

- **App Services**: Hospedagem gerenciada para aplicações web

## 3. **Serviços de Armazenamento Azure**
### **Tipos de Armazenamento**

```
azurecli

# Criando conta de storage
az storage account create \
  --name mystorageaccount \
  --resource-group meu-rg \
  --sku Standard_RAGRS \
  --kind StorageV2
````

- **Blob Storage**: Dados não estruturados em grande escala

- **File Storage**: Compartilhamentos SMB completamente gerenciados

- **Disk Storage**: Discos persistentes para VMs

- **Queue Storage**: Mensagens para comunicação entre aplicações

- **Table Storage**: Armazenamento NoSQL chave-valor

### **Estratégias de Redundância**
|Tipo			|Descrição					|Caso de Uso	|
|---------------|---------------------------|---------------|
|LRS			|Redundância local			|Desenvolvimento/Teste	|
|ZRS			|Redundância de zona		|Aplicações de alta disponibilidade	|
|GRS			|Redundância geográfica		|Backup e disaster recovery	|
|RA-GRS			|Leitura acesso geográfico	|Leitura de dados secundários	|

## **4. Redes e Conectividade Azure**
### **Azure Networking**
```

azurecli
# Criando Virtual Network
az network vnet create \
  --name minha-vnet \
  --resource-group meu-rg \
  --address-prefix 10.0.0.0/16 \
  --subnet-name minha-subnet \
  --subnet-prefix 10.0.1.0/24`

```
- **Virtual Network (VNet)**: Isolamento e segmentação de rede

- **Network Security Groups (NSG)**: Filtragem de tráfego de rede

- **Azure DNS**: Hospedagem de domínios e resolução DNS

- **VPN Gateway**: Conexão site-to-site com redes locais

- **ExpressRoute**: Conectividade privada dedicada

## **5. Identidade, Acesso e Segurança**
### **Microsoft Entra ID**

```
azurecli
# Listando usuários do Entra ID
az ad user list --query "[].{Name:displayName, Email:mail}" --output table

```

- **Autenticação Multifator (MFA)**: Segurança em camadas

- **Single Sign-On (SSO)**: Acesso unificado a múltiplos aplicativos

- **Acesso Condicional**: Políticas baseadas em risco e contexto

- **RBAC (Role-Based Access Control)**: Controle de acesso granular

### **Segurança Avançada**
- **Microsoft Defender for Cloud**: Proteção unificada contra ameaças

- **Azure Policy**: Conformidade e governança automatizada

- **Resource Locks**: Proteção contra exclusão acidental

- **Zero Trust Model**: "Nunca confie, sempre verifique"

## **6. Gerenciamento de Custos e Governança**
### **Otimização de Custos**
```
azurecli
# Criando orçamento mensal
az consumption budget create \
  --name orcamento-mensal \
  --amount 1000 \
  --category cost \
  --time-grain monthly

  ```
- **Azure Pricing Calculator**: Estimativas precisas de custos

- **TCO Calculator**: Análise de economia cloud vs. on-premises

- **Cost Management**: Monitoramento e otimização contínua

- **Tags**: Metadados para agrupamento e alocação de custos

### **Governança e Conformidade**
- **Azure Policy**: Enforcement de padrões organizacionais

- **Azure Blueprints**: Pacotes de governança replicáveis

- **Service Trust Portal**: Documentação de compliance

- **Microsoft Purview**: Governança de dados unificada

## **7. Ferramentas de Gerenciamento e Implantação**
Ferramentas de Linha de Comando
```
bash

# Azure CLI - Gerenciamento multiplataforma
az login
az group list --output table

# Azure PowerShell - Para administradores Windows
Connect-AzAccount
Get-AzResourceGroup | Format-Table

```

### **Infrastructure as Code (IaC)**
```

json
// Exemplo de template ARM
{
  "$schema": "https://schema.management.azure.com/schemas/2019-04-01/deploymentTemplate.json#",
  "contentVersion": "1.0.0.0",
  "resources": [
    {
      "type": "Microsoft.Storage/storageAccounts",
      "apiVersion": "2023-01-01",
      "name": "mystorageaccount",
      "location": "eastus",
      "sku": {
        "name": "Standard_GRS"
      }
    }
  ]
}

```
- **ARM Templates**: Implantação declarativa de recursos

- **Bicep**: Linguagem simplificada para templates ARM

- **Azure DevOps**: CI/CD para infraestrutura como código

- **Azure Arc**: Gerenciamento de recursos híbridos e multi-cloud

## 🛠️ **Ferramentas Dominadas**
- **Portal Azure:** Interface web para gerenciamento

- **Azure CLI**: Linha de comando multiplataforma

- **Azure PowerShell**: Cmdlets para administradores Windows

- **Azure Cloud Shell**: Terminal baseado em navegador

- **VS Code**: Edição de código e templates

- **Git e GitHub**: Controle de versão e colaboração

## **📊 Projetos Desenvolvidos**
1. **Azure VM Configuration**: Dimensionamento e configuração de máquinas virtuais

2. **Azure Storage Solutions**: Implementação de estratégias de armazenamento

3. **Azure Identity & Security**: Configuração de segurança e identidade

4. **Azure Cost Management**: Otimização e monitoramento de custos

5. **Azure Governance**: Implementação de políticas e conformidade

6. **Azure Management Tools**: Domínio de ferramentas de gestão

## **🎯 Competências Desenvolvidas**
- **Architecting**: Design de soluções cloud adequadas

- **Securing**: Implementação de segurança em camadas

- **Managing**: Operação e monitoramento de recursos

- **Optimizing**: Melhoria contínua de performance e custos

- **Governing**: Garantia de conformidade e padrões

## **🔗 Links Úteis e Recursos**
[Microsoft Learn AZ-900](https://learn.microsoft.com/certifications/exams/az-900/)

[Azure Documentation](https://learn.microsoft.com/azure/)

[Azure Quickstart Templates](https://azure.microsoft.com/resources/templates/)

[DIO Learning Platform](https://web.dio.me/)

[GitHub Repository](https://github.com/Dani-dba/formacao-az-900-completa)

## 📝 Conclusão da Jornada
O bootcamp proporcionou uma base sólida em cloud computing com Azure:

1. **Fundamentos Fortes**: Compreensão completa dos conceitos de nuvem

2. **Hands-on Experience**: Experiência prática com serviços Azure

3. **Preparação Certificação**: Conhecimento para AZ-900

4. **Portfólio Profissional**: Projetos reais para demonstrar habilidades

5. **Base para Avançar**: Fundação para certificações avançadas

## 🚀 Próximos Passos
Realizar exame de certificação AZ-900

Explorar certificações especializadas (AZ-104, AZ-305)

Aprofundar em áreas específicas (Security, Data, AI)

Implementar projetos reais em Azure

Participar de comunidades técnicas Azure

*Desenvolvido como parte da Formação Microsoft AZ-900 Certification na DIO - Maio 2024*

![azure fundamentals](https://img.shields.io/badge/Azure-Fundamentals-blue)
![cloudcomputing](https://img.shields.io/badge/Cloud-Computing-orange) ![certificationaz900](https://img.shields.io/badge/Certification-AZ--900-success) ![platformdio](https://img.shields.io/badge/Platform-DIO-brightgreen) ![status](https://img.shields.io/badge/Status-Conclu%C3%ADdo-brightgreen)

## 📞 Contato e Comunidade
[Perfil DIO](https://www.dio.me/users/daniellegoessoares)

[LinkedIn](https://www.linkedin.com/in/danielle-goes/)

[GitHub](https://github.com/Dani-dba)
