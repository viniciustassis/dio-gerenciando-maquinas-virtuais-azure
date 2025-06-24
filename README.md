
# 🚀 Gerenciamento de Máquinas Virtuais no Microsoft Azure

## 📑 Descrição

Este repositório faz parte do desafio de projeto da DIO, no qual foram aplicados os conhecimentos sobre criação, configuração e gerenciamento de máquinas virtuais (VMs) no Microsoft Azure. O objetivo é documentar o passo a passo, anotações e dicas práticas, servindo como material de apoio para estudos e futuras implementações na nuvem.

---

## 🎯 Objetivos do Projeto

- ✅ Aplicar os conceitos de criação e gerenciamento de VMs no Azure.
- ✅ Documentar o processo de forma clara e objetiva.
- ✅ Compartilhar conhecimento utilizando o GitHub como ferramenta de apoio.

---

## 🏗️ Conteúdos Abordados

- ☁️ Criação de Máquinas Virtuais no Azure
- 🛠️ Configuração de Recursos: Disco, Rede e Segurança
- 🔑 Acesso remoto (SSH ou RDP)
- 🔄 Gerenciamento da VM (Iniciar, Parar, Reiniciar, Excluir)
- 💰 Dicas de gerenciamento de custos
- 🔐 Dicas de segurança e boas práticas

---

## 🚀 Passo a Passo

### 🔸 1. Criando uma Máquina Virtual

1. Acesse o portal do Azure: [https://portal.azure.com](https://portal.azure.com)
2. No menu lateral, clique em **"Máquinas Virtuais"**.
3. Clique em **"Criar"** → **"Máquina Virtual"**.
4. Preencha os dados básicos:
   - **Grupo de recursos:** `lab-maquinas-virtuais`
   - **Nome da máquina virtual:** `vm-lab-azure`
   - **Região:** `Brazil South`
   - **Imagem:** `Ubuntu 22.04 LTS` (ou `Windows Server 2022`)
   - **Tamanho:** `Standard B1s` (1 vCPU, 1GB RAM) — econômico para testes.
   - **Usuário:** `azureuser`
   - **Método de autenticação:** senha ou chave SSH.
5. Configure:
   - **Disco:** SSD padrão.
   - **Rede:** criar uma nova VNet, subnet e configurar IP público.
   - **Regras de segurança:** abrir porta 22 (SSH) ou 3389 (RDP).
6. Clique em **"Revisar + criar"** e depois em **"Criar"**.

---

### 🔸 2. Acessando a Máquina Virtual

- 🐧 **Linux (SSH):**

Após criada, copie o IP público e execute:

```bash
ssh azureuser@ip-publico
```

- 🖥️ **Windows (RDP):**

1. Baixe o arquivo de conexão RDP no portal Azure.
2. Execute o arquivo.
3. Insira usuário e senha configurados na criação.

---

### 🔸 3. Gerenciando a VM

- 🔵 No Portal Azure:
  - **Iniciar:** Liga a VM.
  - **Parar:** Desliga a VM, mas mantém os dados.
  - **Reiniciar:** Reinicia o sistema operacional.
  - **Excluir:** Remove a VM e seus recursos (atenção ao grupo de recursos).

- 🔧 Via Azure CLI (exemplo):
```bash
az login
az vm start --name vm-lab-azure --resource-group lab-maquinas-virtuais
az vm stop --name vm-lab-azure --resource-group lab-maquinas-virtuais
```

---

### 🔸 4. Boas Práticas

- ✅ **Gerenciamento de Custos:**
  - Desligue as VMs quando não estiver usando.
  - Monitore o uso pelo **Azure Cost Management**.

- ✅ **Segurança:**
  - Abra somente portas necessárias (ex.: 22 para SSH ou 3389 para RDP).
  - Utilize grupos de segurança (NSG) bem configurados.
  - Sempre prefira autenticação por chave SSH ao invés de senha.

- ✅ **Organização:**
  - Agrupe recursos (VM, disco, IP, VNet) no mesmo grupo de recursos para fácil gerenciamento e limpeza.

---

## 📝 Aprendizados

- ✔️ Criação e configuração de máquinas virtuais na nuvem Azure.
- ✔️ Configuração de rede, disco e regras de acesso.
- ✔️ Gerenciamento dos ciclos de vida da VM (ligar, parar, excluir).
- ✔️ Práticas de segurança e controle de custos.
- ✔️ Uso do GitHub como ferramenta de documentação técnica.

---

## 🔗 Referências

- [Documentação Oficial do Azure – Máquinas Virtuais](https://learn.microsoft.com/pt-br/azure/virtual-machines/)
- [Documentação Azure CLI](https://learn.microsoft.com/pt-br/cli/azure/install-azure-cli)
- [Portal do Microsoft Azure](https://portal.azure.com)

---
