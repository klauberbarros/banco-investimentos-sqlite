# Banco de Dados de Investimentos

## Visão Geral do Projeto

Este repositório contém o projeto de um sistema completo de banco de dados voltado para gestão de investimentos. Ele foi desenvolvido com foco em boas práticas de modelagem relacional, uso de chaves estrangeiras, índices, views e triggers. O banco simula o funcionamento de uma plataforma que gerencia carteiras de investidores, tipos de investimento, instituições financeiras e transações relacionadas.

## Estrutura do Banco de Dados

### Tabelas Criadas

- Investidores: Contém informações pessoais de cada investidor.
- Instituicoes: Armazena dados de bancos, corretoras e outras instituições.
- Tipos_Investimento: Tipos de investimento disponíveis, com seu nível de risco.
- Carteiras: Cada investidor possui uma ou mais carteiras.
- Investimentos: Representa um investimento específico feito por um investidor.
- Transacoes: Registra movimentações financeiras (depósito, saque, rendimento, etc).
- Ativos, Aportes, Resgates, Rendimentos, Metas, Cotacoes: Usadas para análises financeiras e relatórios.

## Scripts Implementados

### Criação de Tabelas (DDL)

- Todas as tabelas possuem PRIMARY KEY bem definidas.
- As FOREIGN KEY estão presentes para garantir integridade referencial.
- Campos com CHECK garantem validações de dados como perfil de risco e tipo de transação.

### Views

- Relatorio_Carteiras: Agrega dados relevantes para visão geral do desempenho de carteiras.

### Triggers

- atualiza_saldo_carteira: Automatiza a atualização de saldo com base nas transações.

### Índices

- Otimizam consultas nas tabelas de investidores, carteiras e transações.

## Consultas SQL Avançadas

- Total de investidores
- Quantidade de ativos por tipo
- Total aportado e saldo por investidor
- Metas e status de atingimento
- Top 5 ativos com maior rendimento
- Evolução mensal do saldo por investidor

Todas as consultas foram construídas com foco em performance e clareza analítica.

## População com Dados (DML)

- Mais de 40 investidores, 5 instituições, 10 ativos financeiros e centenas de registros entre aportes, resgates e rendimentos.
- Simulação realista para testes de relatórios e consultas analíticas.

## Estrutura de Diretórios para GitHub

.
├── README.md
├── schema
│   ├── create_tables.sql
│   ├── views.sql
│   ├── triggers.sql
│   └── indexes.sql
├── data
│   ├── insert_investidores.sql
│   ├── insert_instituicoes.sql
│   ├── insert_ativos.sql
│   ├── insert_investimentos.sql
│   └── insert_transacoes.sql
├── queries
│   ├── relatorios_gerais.sql
│   └── relatorios_analiticos.sql
├── LICENSE
└── .gitignore

## Instruções para Execução

1. Clone o repositório:

   git clone https://github.com/seuusuario/banco-investimentos.git

2. Execute os scripts na ordem:

   cd banco-investimentos/schema
   sqlite3 investimentos.db < create_tables.sql
   sqlite3 investimentos.db < views.sql
   sqlite3 investimentos.db < triggers.sql

   cd ../data
   sqlite3 investimentos.db < insert_investidores.sql
   ...

3. Rode as queries em queries/*.sql para testar e gerar relatórios.

## Requisitos

- SQLite ou PostgreSQL (adaptável)
- Editor SQL como DBeaver ou SQLiteStudio

## Possíveis Extensões Futuras

- API REST para consulta das carteiras
- Integração com frontend em React ou Vue.js
- Dashboards com Power BI ou Metabase

## Licença

Este projeto está sob a Licença MIT.
