"# Projeto-E-commerce---Dio-Suzano" 
Sistema de Gestão de Pedidos - Modelagem de Banco de Dados

📋**Descrição do Projeto**
Este projeto é uma modelagem de banco de dados desenvolvida para um sistema de gestão de pedidos no setor de e-commerce. A proposta é gerenciar as informações relacionadas a clientes, produtos, fornecedores, pedidos e pagamentos, com suporte a diferentes tipos de clientes (Pessoa Física e Jurídica) e múltiplas formas de pagamento.

A modelagem foi criada utilizando a ferramenta DBeaver, baseada em conceitos de banco de dados relacionais, e otimizada para atender aos requisitos de:

Controle de estoque,
Rastreamento de entregas,
Cadastro de fornecedores,
Flexibilidade nas transações de pagamento.

🗂️**Entidades e Relacionamentos**

1. **Tabela cliente**
Armazena informações de clientes, com suporte para identificação como Pessoa Física ou Jurídica:

**Campos:**

    idcliente (PK)
    
    identificação (PF ou PJ)
    
    endereço
    
    nome
    
    Tipo_doc (CPF ou CNPJ)
    
    n_documento

2. **Tabela pedido**
Gerencia os pedidos realizados pelos clientes:

**Campos:**

    idpedido (PK)
    
    status_pedido (Ex: "Pendente", "Enviado", "Concluído")
    
    descrição
    
    prioridade
    
    Total_do_pedido
    
    data_do_pedido
    
    frete_valor
    
    idcliente (FK para cliente)
    
    cod_rastreio
    
    idpagamento (FK para pagamento)

3. **Tabela pagamento**
Controla as formas e o status de pagamentos:

**Campos:**

    idpagamento (PK)
    
    tipo_de_pagamento (Ex: "Cartão", "Boleto", "Pix")
    
    forma_de_pagamento
    
    status_de_pagamento (Ex: "Aprovado", "Pendente")

4. **Tabela produto**
Armazena os detalhes dos produtos disponíveis:

**Campos:**

    idproduto (PK)
    
    categoria
    
    descrição
    
    quantidade
    
    valor
    
    unidade_de_medida

5. **Tabela estoque**
Gerencia o controle de estoque:

**Campos:**

    idestoque (PK)
    
    quantidade
    
    almoxarifado

6. **Tabela estoque_e_produto**
Tabela intermediária para relacionar estoque e produto:

**Campos:**

    idestoque (FK para estoque)
    
    idproduto (FK para produto)
    
    quantidade

7. **Tabela relação_de_produto_pedido**
Relaciona produtos com pedidos:

**Campos:**

    idpedido (FK para pedido)
    
    idproduto (FK para produto)

8. **Tabela fornecedor**
Registra fornecedores dos produtos:

**Campos:**

    idfornecedor (PK)
    
    cnpj_cpf
    
    razao_social
    
    contato

9. **Tabela disponibilizando_produto**
Relaciona fornecedores com os produtos que disponibilizam:

**Campos:**

    idproduto (FK para produto)
    
    idfornecedor (FK para fornecedor)

10. **Tabela vendedores_terceiros**
Gerencia vendedores terceiros:

**Campos:**

    idvendedorterceiro (PK)
    
    local
    
    razao_social

11. **Tabela produtos_vendedor_terce**
Relaciona vendedores terceiros com produtos e pedidos:

**Campos:**

    idvendedorterceiro (FK para vendedores_terceiros)
    
    idproduto (FK para produto)
    
    idpedido (FK para pedido)
    
    quantidade

📊 **Diagrama de Relacionamento**

🛠️ **Tecnologias Utilizadas**
Ferramenta de Modelagem: DBeaver
Banco de Dados: MySQL
