# DesafioDioMecanica
# 📌 Modelo Conceitual - Oficina Mecânica  ## 📚 Descrição Este repositório contém o esquema conceitual para um sistema de controle e gerenciamento de ordens de serviço em uma oficina mecânica.  
# 📌 Modelo Conceitual - Oficina Mecânica

## 📚 Descrição
        Objetivo:
        Cria o esquema conceitual para o contexto de oficina com base na narrativa fornecida

## Narrativa:
        Sistema de controle e gerenciamento de execução de ordens de serviço em uma oficina mecânica
        Clientes levam veículos à oficina mecânica para serem consertados ou para passarem por revisões  periódicas
        Cada veículo é designado a uma equipe de mecânicos que identifica os serviços a serem executados e preenche uma OS com data de entrega.
        A partir da OS, calcula-se o valor de cada serviço, consultando-se uma tabela de referência de mão-de-obra
        O valor de cada peça também irá compor a OSO cliente autoriza a execução dos serviços
        A mesma equipe avalia e executa os serviços
        Os mecânicos possuem código, nome, endereço e especialidade
        Cada OS possui: n°, data de emissão, um valor, status e uma data para conclusão dos trabalhos.
        
## Este repositório contém o esquema conceitual para um sistema de controle e gerenciamento de ordens de serviço em uma oficina mecânica.

## 🛠️ Requisitos do Sistema
1. Clientes levam veículos à oficina para conserto ou revisão periódica.
2. Cada veículo é designado a uma **equipe de mecânicos** que identifica e registra os serviços necessários em uma OS.
3. A OS inclui data de entrega, valores calculados a partir da tabela de mão de obra e peças necessárias.
4. O cliente deve autorizar a execução dos serviços.
5. A equipe avalia e executa os serviços conforme a OS.

## 🏷️ Estrutura do Modelo
### 🔹 Clientes
    - **IdCliente** (PK)
    - **NomeCliente**
    - **Telefone**

### 🔹 Endereços
    - **IdEndereco** (PK)
    - **Rua**
    - **Número**
    - **Bairro**
    - **Cidade**
    - **Estado**
    - **CEP**

### 🔹 Cliente_Endereço
      - **IdCliente** (FK)
      - **IdEndereço** (FK)

### 🔹 MecanicoEndereco
- **IdMecânico** (FK)
- **IdEndereço** (FK)

### 🔹 Veículos
      - **IdVeiculo ** (PK)
      - **Placa** (único)
      - **Modelo**
      - **Ano**
      - **IdCliente** (FK)

### 🔹 EquipeMecanicos
      - **IdEquipeMecanicos ** (PK)
      - **NomeEquipe**

### 🔹 Mecanicos
      - **IdMecanico** (PK)
      - **Nome**
      - **Especialidade**
      - **IdEquipeMecanico** (FK)

### 🔹 OrdemServiço (OS)
    - **IdOrdemServiço ** (PK)
    - **Data de Emissão**
    - **Valor Total**
    - **Status**
    - **Data de Conclusão**
    - **IdVeiculo** (FK)
    - **IdEquipe** (FK)

### 🔹 ServiçoPrestado
    - **IdServiçoPrestado ** (PK)
    - **Descrição**
    - **Valor Mão de Obra**
    - **IdOrdemServico** (FK)

### 🔹 PecaUtilizada
    - **IdPecaUtilizada ** (PK)
    - **Nome**
    - **Valor**
    - ** IdOrdemSservico ** (FK)

## 🎯 Relacionamentos
    - Um **cliente** pode ter vários **endereços**, e um endereço pode pertencer a vários clientes (relação muitos para muitos).
    - Um **mecânico** pode ter um ou mais **endereços** (relação muitos para muitos).
    - Um **cliente** pode ter vários **veículos**.
    - Um **veículo** pode ter várias **ordens de serviço**.
    - Uma **ordem de serviço** pode ter múltiplos **serviços prestados** e **peças utilizadas**.
    - Um **mecânico** faz parte de uma **equipe**.
    - Uma **equipe** é responsável por várias **ordens de serviço**.

![Cria o esquema conceitual para o contexto de oficina com base na narrativa fornecida](https://github.com/user-attachments/assets/87a6bd0a-8a1f-4cc3-a5b0-752536589e4a)
