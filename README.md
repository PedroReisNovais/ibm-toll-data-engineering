# IBM Toll Data Engineering

Pipeline ETL de dados de pedágio desenvolvido em uma atividade prática da IBM Data Engineering.

## Visão geral

O projeto implementa uma DAG do **Apache Airflow** que extrai dados de três formatos diferentes, consolida os resultados e aplica uma transformação final. O código principal está em `dags/ETL_toll_data.py`.

## Pipeline

```text
tolldata.tgz
    |
    v
unzip_data
    |
    v
extract_data_from_csv
    |
    v
extract_data_from_tsv
    |
    v
extract_data_from_fixed_width
    |
    v
consolidate_data
    |
    v
transform_data
    |
    v
transformed_data.csv
```

A ordem das tarefas é definida explicitamente na DAG.

## Etapas

- **Unzip:** descompacta o conjunto de dados de entrada.
- **CSV:** seleciona os campos 1–4 de `vehicle-data.csv`.
- **TSV:** seleciona os campos 5–7 de `tollplaza-data.tsv` e converte tabulações para vírgulas.
- **Fixed width:** extrai as posições 59–67 de `payment-data.txt`.
- **Consolidação:** combina as três extrações em `extracted_data.csv`.
- **Transformação:** converte o quarto campo para letras maiúsculas e gera `transformed_data.csv`.

## Tecnologias e conceitos

- Python
- Apache Airflow
- Bash / Linux
- ETL
- CSV e TSV
- Arquivos fixed-width
- `cut`, `tr`, `paste` e `awk`
- Git e GitHub

## Estrutura

```text
ibm-toll-data-engineering/
├── dags/
│   └── ETL_toll_data.py
├── data/
│   └── transformed_data.csv
├── evidence/
│   └── screenshots da execução
├── .gitignore
└── README.md
```

## Evidências

As evidências produzidas durante a atividade incluem a definição da DAG, configuração dos argumentos, tarefas de extração, consolidação e transformação, cadeia de dependências e execuções do Airflow com status de sucesso.

## Resultado

A DAG `ETL_toll_data` foi configurada para execução diária, sem catchup, com retry em caso de falha.

O pipeline gera como saída `transformed_data.csv`, contendo os registros consolidados e transformados. O arquivo de saída foi incluído na raiz do repositório para facilitar sua inspeção.

### Competências demonstradas

- Construção de pipeline ETL;
- orquestração de workflow com Apache Airflow;
- processamento de múltiplos formatos de dados;
- manipulação de dados via ferramentas Unix;
- definição de dependências entre tarefas;
- validação de execução e análise de resultados;
- versionamento e documentação técnica com Git/GitHub.

## Autor

**Pedro Reis Novais**

Projeto acadêmico desenvolvido como parte da formação IBM em Data Engineering.
