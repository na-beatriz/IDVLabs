# 📦 Projeto de Engenharia de Dados – Pipeline de Vendas

## 🚀 Descrição

Este projeto implementa uma arquitetura de dados moderna simulando o pipeline de uma operação de vendas. O fluxo contempla desde a ingestão de dados brutos (banco de dados e arquivos CSV), até o enriquecimento e padronização dos dados para consumo analítico. 

A estrutura segue o modelo em camadas: Landing → Bronze → Silver → Gold.

---

## 🎯 Objetivo do Projeto

- Ingerir dados de diferentes fontes: banco MariaDB e carga fria (CSV).
- Realizar o tratamento e padronização dos dados.
- Validar informações críticas como CPF e valores monetários.
- Enriquecer os dados com indicadores de performance.
- Preparar os dados para consumo em ferramentas de BI.

---

## 🛠️ Tecnologias e Ferramentas

- Python 3.x
- Pandas
- NumPy
- Jupyter Notebook
- MariaDB
- Formato Parquet
- Visual Studio Code

---

## 📂 Pipeline de Dados

### ☁️ Camada Landing

- Ingestão de dados brutos a partir do banco de dados (MariaDB).
- Upload de arquivos CSV com dados complementares (clientes e produtos).
- Fusão de cargas e persistência inicial no Data Lake.

### 🟫 Camada Bronze

- Tratamento leve e unificação das bases.
- Remoção de nulos, ajustes de tipos e estruturação.
- Dados ainda próximos do formato original, mas organizados.

### ⚙️ Camada Silver

- Validação de CPF.
- Padronização de valores monetários (remoção de decimais e separadores).
- Conversão de campos para tipos corretos (inteiros, datas).
- Separação de data e hora.
- Limpeza de caracteres especiais.

### 🟡 Camada Gold

- Enriquecimento da base:
  - `lucro_bruto_item = preco_venda - preco_custo`
  - `margem_lucro_percentual = (lucro_bruto_item / preco_custo) * 100`
- Exportação em formato Parquet otimizado para análise.

---

## 🗂️ Estrutura de Diretórios

📁 IDVLabs/
├──📁 data_carga_fria/
│ ├── idv_store_clientes_cf.csv
│ └── idv_store_produtos_cf.csv
├──📁 data_lake/
│ ├──📁 landing/
│ │ ├── data_landing.csv
│ │ └── script_landing.ipynb
│ ├──📁 bronze/
│ │ ├── data_bronze/
│ │ └── script_bronze.ipynb
│ ├──📁 silver/
│ │ ├── data_silver/
│ │ └── script_silver.ipynb
│ └──📁 gold/
│ ├── data_gold/
│ ├── idv_store_fato_venda_final.parquet
│ └── script_gold.ipynb

---

## 📈 Resultados e Benefícios

- Dados organizados e documentados em todas as camadas do pipeline.
- Base de vendas com estrutura analítica e colunas enriquecidas.
- Preparação ideal para integração com dashboards e análises exploratórias.
- Simulação completa de um fluxo típico de engenharia de dados corporativa.

---

## ✅ Próximos Passos

- Adicionar particionamento por data e/ou categoria na camada Gold.
- Criar uma camada de apresentação (presentation layer) para dashboards.
- Automatizar o pipeline com Prefect ou Apache Airflow.
- Implementar testes de qualidade de dados com regras específicas (DQ checks).

---

## 🔄 Próximas Atualizações

- 📘 Criação de um `data_dictionary.md` contendo a descrição das colunas e regras de transformação.
- 📊 Construção de painéis de análise com Power BI conectando diretamente a camada Gold.

---

## 🏷️ Licença

Este projeto tem fins educacionais e demonstração técnica.  
Todos os dados utilizados são fictícios e simulados.

---

## 🤝 Contribuição

Sugestões de melhoria, refatoração de scripts e novas ideias são bem-vindas.  
Abra uma issue ou envie um pull request!