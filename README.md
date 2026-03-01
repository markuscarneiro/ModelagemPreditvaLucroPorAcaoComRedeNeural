# Modelagem LSTM

![Python](https://img.shields.io/badge/Python-3.12+-3776AB?logo=python&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.19-FF6F00?logo=tensorflow&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2.3-150458?logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-2.1-013243?logo=numpy&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-1.7-F7931E?logo=scikitlearn&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.10-11557C)
![Status](https://img.shields.io/badge/Status-Ativo-success)

Projeto de modelagem de séries temporais para previsão de **EPS (Earnings Per Share)** com rede neural **LSTM (Long Short-Term Memory)** em Python.

https://www.deeplearningbook.com.br/arquitetura-de-redes-neurais-long-short-term-memory/

## Objetivo

Treinar um modelo recorrente para aprender o comportamento histórico do EPS e gerar:

- previsões no conjunto de treino e teste;
- avaliação com RMSE;
- projeção de próximos períodos (forecast de 2 anos).

## Estrutura do Projeto

```text
.
├── ModelagemLSTM.py      # Script principal de treinamento, avaliação e forecast
├── dataset.csv           # Base de dados com colunas de ano e EPS
├── requirements.txt      # Dependências fixadas
└── README.md             # Documentação do projeto
```

## Requisitos

- Python 3.12+
- Pip atualizado
- Dependências listadas em `requirements.txt`

## Instalação

### Opção 1 — Ambiente virtual com venv

```bash
python -m venv .venv
```

Ativação no Windows (PowerShell):

```powershell
.\.venv\Scripts\Activate.ps1
```

Ativação no Linux/macOS:

```bash
source .venv/bin/activate
```

Instale as dependências:

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

### Opção 2 — Ambiente com conda

```bash
conda create --name modelagemlstm python=3.12 -y
conda activate modelagemlstm
pip install -r requirements.txt
```

## Execução

No diretório do projeto, execute:

```bash
python ModelagemLSTM.py
```

## Pipeline Implementado

1. Carregamento do dataset (`dataset.csv`)
2. Seleção da série temporal de EPS
3. Divisão temporal em treino (80%) e teste (20%)
4. Normalização com `MinMaxScaler`
5. Construção das janelas temporais (`look_back = 1`)
6. Treinamento de LSTM + camada densa
7. Avaliação com RMSE em treino e teste
8. Visualização gráfica (real vs previsto)
9. Forecast iterativo de 2 períodos

## Saídas Esperadas

- Logs de treinamento do TensorFlow
- RMSE de treino e teste
- Gráfico com série original e previsões
- Valores previstos para os próximos 2 anos

## Reprodutibilidade

O script define seed fixa (`SEED = 42`) para reduzir variabilidade entre execuções.

## Licença

Este projeto está disponível para uso educacional e portfólio. Caso deseje, adicione um arquivo `LICENSE` apropriado ao seu repositório.

