# 💻 Gerenciamento de Máquinas Virtuais no Microsoft Azure

## 📘 Descrição

Este repositório foi criado como parte de um laboratório prático para documentar o aprendizado sobre **máquinas virtuais (VMs)** no Azure. Ele contém resumos, anotações, dicas e capturas de tela que auxiliam na criação, configuração e gerenciamento de VMs para ambientes de estudo e produção.

---

## 📌 Visão Geral

As VMs do Azure fazem parte da camada de **Infraestrutura como Serviço (IaaS)** e permitem executar sistemas operacionais e aplicativos personalizados em um ambiente virtualizado. São ideais para workloads que exigem controle total do sistema operacional e configurações específicas de hardware.

---

## 🛠️ Criação e Configuração de Máquinas Virtuais

### 🔧 Planejamento
- **Região**: Escolha próxima ao usuário final para reduzir latência.
- **Rede**: Utilize redes virtuais (VNets) e sub-redes previamente configuradas.
- **Tamanho da VM (SKU)**: Escolha baseado em CPU, RAM, e uso (ex: memória intensiva, computação etc).

### 💽 Armazenamento
- **Disco do SO (C:)** – essencial para o sistema operacional.
- **Disco temporário (D:)** – dados são apagados ao reiniciar.
- **Discos de dados** – adicionais, não precisam de reboot para anexar.
- **Tipos de discos**: HDD, SSD Standard, SSD Premium, SSD Ultra.

### 🔐 Conexão e Segurança
- **Azure Bastion**: Acesso via navegador sem expor IP público.
- **Windows**: RDP via porta 3389.
- **Linux**: SSH com chave pública ou senha.
- **Criptografia**: Azure Disk Encryption para proteger dados em repouso.

---

## 🔁 Modelos de Serviço

| Modelo | Descrição |
|--------|-----------|
| **IaaS** | Infraestrutura como serviço – você gerencia a VM e o SO. |
| **PaaS** | Plataforma como serviço – foco no banco de dados ou aplicação, sem gerenciar SO. |
| **SaaS** | Software como serviço – soluções prontas como o Microsoft 365. |

---

## ⚙️ Alta Disponibilidade e Tolerância a Falhas

### ✅ Availability Set
- Protege contra falhas de hardware e atualizações simultâneas.
- Garante SLA de 99,95%.
- Usa **domínios de falha** (hardware) e **domínios de atualização** (software).
- Ideal para balanceamento de carga entre instâncias.

### 🌍 Availability Zones
- Datacenters distintos dentro de uma mesma região.
- Rede, energia e refrigeração independentes.
- SLA de 99,99%.
- Protege contra falhas em datacenters inteiros.

---

## 📈 Escalabilidade

### 🔁 Escala Vertical
- Aumenta recursos da **mesma VM** (RAM, CPU).
- Requer reinicialização.

### 🔀 Escala Horizontal
- Adiciona ou remove instâncias automaticamente com base em métricas.
- Ideal para aplicações com carga variável.

### 📦 VM Scale Sets (VMSS)
- Conjuntos de VMs idênticas com escalabilidade automática.
- Integra-se a balanceadores de carga.
- Suporte para instâncias spot, escalonamento mínimo/máximo e dimensionamento automático.

---

## 💡 Boas Práticas

- **Evite VMs Spot em produção** – são desalocadas sem aviso.
- **Use discos gerenciados** – maior desempenho e facilidade de backup.
- **Configure alertas** – monitore CPU, memória e uso de disco.
- **Implemente redundância** – distribua cargas entre zonas e conjuntos de disponibilidade.

---

## 🔗 Referências Oficiais

- [Overview de Availability Sets](https://learn.microsoft.com/azure/virtual-machines/availability-set-overview)
- [Autoscale com VM Scale Sets](https://learn.microsoft.com/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-autoscale-overview)
- [Responsabilidade Compartilhada no Azure](https://learn.microsoft.com/azure/security/fundamentals/shared-responsibility)
- [Disco Temporário no Azure](https://learn.microsoft.com/azure/virtual-machines/azure-vms-no-temp-disk)

---
