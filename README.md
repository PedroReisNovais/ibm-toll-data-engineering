# IBM Toll Data Engineering

Projeto de engenharia de dados desenvolvido como atividade prática da IBM, com foco na construção de um pipeline ETL para dados de pedágio.

## Objetivo

Construir um fluxo de dados capaz de extrair informações provenientes de diferentes formatos de arquivo, consolidá-las, transformá-las e orquestrar a execução do pipeline.

## Tecnologias

- Linux / Shell
- Python
- Apache Airflow
- ETL (Extract, Transform, Load)
- CSV
- TSV
- Fixed-width files
- Git & GitHub

## Pipeline ETL

O projeto trabalha com três fontes de dados:

1. **CSV** — extração de dados tabulares.
2. **TSV** — extração de dados delimitados por tabulação.
3. **Fixed-width** — extração de registros em posições fixas.

Após a extração, os dados são consolidados e transformados para gerar o conjunto final utilizado pelo pipeline.

### Fluxo

```text
CSV ───────────┐
TSV ───────────┼─> Extract ─> Consolidate ─> Transform ─> Output
Fixed Width ───┘
                         │
                    Apache Airflow
                    (orchestration)
```

## Apache Airflow

O pipeline é definido como uma DAG no Apache Airflow. As tarefas representam as etapas de extração, consolidação e transformação, permitindo controlar dependências e acompanhar as execuções.

## Estrutura planejada

```text
ibm-toll-data-engineering/
├── README.md
├── dags/
│   └── ETL_toll_data.py
├── data/
│   └── transformed_data.csv
└── evidence/
    └── screenshots do projeto
```

## Competências demonstradas

- Construção de pipelines ETL
- Processamento de múltiplos formatos de dados
- Automação de tarefas de engenharia de dados
- Definição e execução de DAGs
- Orquestração com Apache Airflow
- Organização de projeto para versionamento com Git

## Contexto

Projeto desenvolvido durante a formação IBM em Data Engineering, como exercício prático de criação e orquestração de pipelines de dados.

---

**Autor:** Pedro Reis Novais
