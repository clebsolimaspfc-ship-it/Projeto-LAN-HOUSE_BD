# Sistema de Gestão Lan House

> Projeto de modelagem de banco de dados, gerenciamento da Lan House.

---

## Projeto de Banco de Dados — DER, Normalização e Sript.

---

# Faculdade 

**UNIBRA IBGM**

Curso: Análise e Desenvolvimento de Sistemas

Disciplina: Banco de Dados

Turma: ADS2N

---

# Equipe

* Integrante 1: Clebson Alves De Lima
* Integrante 2: Jessica Natália Teófilo da S de Moura
* Integrante 3: Geovani Emanuel de Souza

Professor(a): Fransisco Erberto

---

# Título do Projeto

# Sistema Lan House

Projeto acadêmico desenvolvido com foco em:

* Modelagem de Banco de Dados
* Normalização (1FN, 2FN e 3FN)
* Construção de DER
* Integridade Referencial
* Segurança de Dados
* Auditoria de Sistema
* Constraints Avançadas
* Script DDL e DML

---

# Objetivo do Projeto

O objetivo do sistema é gerenciar uma Lan House de maneira segura, organizada e eficiente, permitindo:

* Cadastro de clientes
* Controle de computadores
* Gerenciamento de sessões
* Controle de consumo de produtos
* Registro de pagamentos
* Controle de torneios
* Sistema de auditoria (audit_log)
* Controle administrativo

O projeto foi desenvolvido seguindo boas práticas de modelagem relacional e normalização de banco de dados.

---

#  Formas Utilizadas

| Tecnologia           | Finalidade                      |
| -------------------- | ------------------------------- |
| MySQL                | Banco de Dados                  |
| SQL                  | Criação das tabelas e consultas |
| GitHub               | Versionamento do projeto        |
| BRMODELO             | Criação do DER                  |

---

# Estrutura do Banco de Dados

O banco de dados foi modelado utilizando:

* Entidades fortes
* Entidades fracas
* Chaves primárias e estrangeiras
* Cardinalidades
* Constraints
* Auditoria de eventos

---

# Entidades do Sistema

## Clientes

Responsável pelo armazenamento dos dados dos clientes cadastrados.

### Principais atributos

* id_cliente
* nome
* cpf
* email
* telefone
* data_cadastro

---

## Administradores

Responsável pelos usuários administrativos do sistema.

### Principais atributos

* id_admin
* nome
* email
* senha_hash
* nivel_acesso
* ultimo_login

---

## Computadores

Tabela responsável pelos computadores da Lan House.

### Principais atributos

* id_computador
* nome
* especificacoes
* status
* preco_hora

---

## Sessoes

Controla as sessões realizadas pelos clientes.

### Principais atributos

* id_sessao
* inicio
* fim
* valor_total
* status

---

## Produtos

Armazena os produtos vendidos na Lan House.

### Principais atributos

* id_produto
* nome
* categoria
* preco
* estoque

---

## Forma_pagamento

Responsável pelas formas de pagamento utilizadas.

### Principais atributos

* id_forma_pagamento
* nome
* descricao

Exemplos:

* PIX
* Crédito
* Débito
* Dinheiro

---

## Consumo

Representa os produtos consumidos durante uma sessão.

### Principais atributos

* id_consumo
* quantidade
* subtotal
* data_consumo

---

## Torneios

Tabela responsável pelos campeonatos da Lan House.

### Principais atributos

* id_torneio
* nome
* jogo
* data_torneio
* premio
* descricao

---

## Inscricoes

Tabela associativa entre clientes e torneios.

### Principais atributos

* id_inscricao
* data_inscricao

---

## Audit_log

Responsável pela auditoria do sistema.

### Principais atributos

* id_log
* tabela_afetada
* acao
* descricao
* ip_origem
* data_evento

---

# Diagrama Entidade-Relacionamento (DER)

## Visão Geral

O DER foi desenvolvido utilizando:

* cardinalidades corretas
* entidades fracas
* normalização completa
* integridade referencial
* auditoria do sistema

### Entidades do DER

```text
clientes
administradores
computadores
sessoes
produtos
forma_pagamento
consumo
torneios
inscricoes
audit_log
```
---

### MODELAGEM (DER)

<img width="3508" height="2479" alt="modelo_conceitual_brmw" src="https://github.com/user-attachments/assets/b632b66a-442a-431b-834f-975d3cbb68bf" />


