# desafio-2-mysql-dio-modelagem


---

## **Esquema Conceitual do Sistema de Oficina Mecânica**

### Entidades e Atributos:

1. **Cliente**  
   - ID_Cliente (PK)  
   - Nome  
   - CPF/CNPJ  
   - Endereço  
   - Telefone  

2. **Veículo**  
   - ID_Veículo (PK)  
   - Placa  
   - Modelo  
   - Ano  
   - ID_Cliente (FK)  

3. **Mecânico**  
   - ID_Mecânico (PK)  
   - Nome  
   - Endereço  
   - Especialidade  

4. **Equipe**  
   - ID_Equipe (PK)  
   - Nome_Equipe  
   - ID_Mecânico (FK)  

5. **Ordem de Serviço (OS)**  
   - ID_OS (PK)  
   - Data_Emissão  
   - Valor_Total  
   - Status (Em andamento, Concluído, Cancelado)  
   - Data_Conclusão  
   - ID_Veículo (FK)  
   - ID_Equipe (FK)  

6. **Serviço**  
   - ID_Serviço (PK)  
   - Descrição_Serviço  
   - Valor_Referência  

7. **Peça**  
   - ID_Peça (PK)  
   - Nome_Peça  
   - Valor  

8. **Serviço_OS** (Relacionamento entre OS e Serviço)  
   - ID_OS (FK)  
   - ID_Serviço (FK)  
   - Quantidade  
   - Subtotal  

9. **Peça_OS** (Relacionamento entre OS e Peça)  
   - ID_OS (FK)  
   - ID_Peça (FK)  
   - Quantidade  
   - Subtotal  

---

### **Relacionamentos:**

1. **Cliente** possui **Veículo**:  
   - Um cliente pode ter um ou mais veículos.  
   - Relacionamento: 1:N (um para muitos).  

2. **Veículo** é associado a uma **OS**:  
   - Cada veículo pode gerar várias ordens de serviço ao longo do tempo.  
   - Relacionamento: 1:N (um para muitos).  

3. **Equipe** realiza a **OS**:  
   - Cada ordem de serviço é atribuída a uma equipe.  
   - Relacionamento: 1:N (um para muitos).  

4. **Mecânico** faz parte de uma **Equipe**:  
   - Um mecânico pode pertencer a uma ou mais equipes.  
   - Relacionamento: N:M (muitos para muitos).  

5. **OS** inclui um ou mais **Serviços** e **Peças**:  
   - Cada ordem de serviço pode ter vários serviços e peças associadas.  
   - Relacionamentos intermediários: **Serviço_OS** e **Peça_OS** para detalhar a quantidade e o valor de cada item.  

---


### **Sistema de Controle de Ordem de Serviço - Oficina Mecânica**

Este projeto apresenta um esquema conceitual para o gerenciamento de ordens de serviço em uma oficina mecânica. O objetivo é garantir que o processo de conserto e revisão de veículos seja organizado e eficiente. O sistema envolve o cadastro de clientes, veículos, mecânicos e peças, além de permitir o controle das ordens de serviço (OS). Cada OS é gerenciada por uma equipe de mecânicos e contém todos os serviços e peças necessários para o atendimento.

### **Contexto do Esquema Conceitual:**

- Os **clientes** levam seus veículos para a oficina para conserto ou revisão.
- Cada **veículo** é atribuído a uma **equipe de mecânicos**, que identifica os serviços necessários e gera uma ordem de serviço (OS).
- A OS contém todos os serviços e peças utilizados, com seus respectivos valores.
- O sistema permite consultar uma tabela de referência para calcular o custo da mão de obra e das peças.
- A conclusão dos serviços depende da autorização do cliente e do acompanhamento da equipe responsável.

### **Tecnologias:**
- Ferramentas para modelagem de banco de dados, como MySQL Workbench, Draw.io ou DBDesigner.
- O esquema conceitual pode ser implementado posteriormente em banco de dados SQL (como MySQL ou PostgreSQL) ou NoSQL.

---
