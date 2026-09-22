# Analista Bolsa de Valores

Projeto educacional em Python para estudar análise fundamentalista, ciência de dados, machine learning e backtesting aplicados a ações.

> Este repositório tem finalidade de estudo e portfólio. Não constitui recomendação de investimento, compra ou venda de ativos.

## Tags

`python` `vibecoding` `vibecode` `machine-learning` `data-science` `finance` `b3` `fundamental-analysis`

## Objetivo

Construir um pipeline reproduzível capaz de:

- coletar ou importar fundamentos e cotações históricas;
- organizar dados por empresa e período;
- criar features fundamentalistas;
- treinar e comparar modelos de machine learning;
- validar os modelos com separação temporal;
- simular uma carteira;
- comparar o resultado com um benchmark;
- gerar métricas, gráficos e relatórios.

O ponto de partida é a série **Projeto Inteligência Artificial em Ações**, da Hashtag Programação. O projeto será reproduzido primeiro e depois modernizado.

## Série de referência

1. [Aula 1/4 — Passo a Passo do Projeto e Resultados](https://www.youtube.com/watch?v=nXMecZ9oBmQ&list=PLpdAy0tYrnKw4UVhAdP7rMf01wI_AOcHE)
2. [Aula 2/4 — Fundamentos de Empresas do IBOVESPA com Python](https://www.youtube.com/watch?v=wz5_MOWYias)
3. [Aula 3/4 — Análise Exploratória de Empresas com Python](https://www.youtube.com/watch?v=NrXoxWpVUR0)
4. [Aula 4/4 — Carteira de Ações Python que ganha do IBOVESPA](https://www.youtube.com/watch?v=6Lv5F1C340Y)

## Arquitetura prevista

```text
Fontes de dados
      ↓
Ingestão
      ↓
data/raw
      ↓
Tratamento
      ↓
data/processed
      ↓
EDA
      ↓
Feature Engineering / Selection
      ↓
Split temporal
      ↓
Treino e comparação de modelos
      ↓
Tuning
      ↓
Backtest fora da amostra
      ↓
Carteira simulada + Benchmark
      ↓
Relatório
```

## Stack inicial

- Python 3.12+
- pandas
- numpy
- scikit-learn
- matplotlib
- plotly
- Jupyter
- pytest
- ruff
- pydantic-settings

A stack poderá mudar conforme o projeto evoluir.

## Estrutura planejada

```text
analistabolsadevalores/
├── README.md
├── pyproject.toml
├── .env.example
├── data/
│   ├── raw/
│   ├── interim/
│   └── processed/
├── notebooks/
│   ├── 01_ingestao.ipynb
│   ├── 02_tratamento.ipynb
│   ├── 03_eda.ipynb
│   ├── 04_features.ipynb
│   └── 05_modelagem.ipynb
├── src/
│   ├── data/
│   ├── features/
│   ├── models/
│   ├── backtest/
│   └── reporting/
├── tests/
└── docs/
```

## Roadmap

### 0. Reprodução do projeto original

- [ ] Reproduzir Aula 1
- [ ] Reproduzir Aula 2
- [ ] Reproduzir Aula 3
- [ ] Reproduzir Aula 4
- [ ] Registrar resultado-base

### 1. Engenharia de dados

- [ ] Definir universo de ativos
- [ ] Definir fontes de fundamentos
- [ ] Definir fonte de cotações
- [ ] Criar camada raw
- [ ] Criar validações de qualidade
- [ ] Padronizar empresa, ticker, período e datas

### 2. Dataset de modelagem

- [ ] Criar alvo
- [ ] Garantir ausência de vazamento temporal
- [ ] Tratar valores ausentes
- [ ] Criar features derivadas
- [ ] Criar pipeline reproduzível

### 3. EDA

- [ ] Distribuições
- [ ] Correlações
- [ ] Outliers
- [ ] Missing values
- [ ] Desbalanceamento do alvo
- [ ] Estabilidade ao longo do tempo

### 4. Modelagem

Baseline obrigatório:

- DummyClassifier

Modelos iniciais:

- Logistic Regression
- Decision Tree
- Random Forest
- Gradient Boosting
- HistGradientBoosting
- SVM

### 5. Validação temporal

- [ ] Train/validation/test temporal
- [ ] Walk-forward validation
- [ ] Teste fora da amostra
- [ ] Comparação de estabilidade por período

### 6. Backtesting

- [ ] Regra de rebalanceamento
- [ ] Limite de ativos
- [ ] Pesos
- [ ] Custos configuráveis
- [ ] Benchmark
- [ ] Retorno acumulado
- [ ] Volatilidade
- [ ] Drawdown

### 7. Produto

- [ ] CLI
- [ ] Relatório HTML/PDF
- [ ] Dashboard opcional
- [ ] API opcional
- [ ] Automação da atualização dos dados

## Princípios do projeto

1. Dados futuros não podem vazar para o passado.
2. Split principal deve respeitar a ordem temporal.
3. Backtest não é prova de rentabilidade futura.
4. Acurácia isolada não define a qualidade da estratégia.
5. Todo experimento deve ser reproduzível.
6. Fontes de dados devem ficar desacopladas da lógica dos modelos.
7. O projeto deve comparar modelos com um baseline simples.

## Como executar

O projeto ainda está em fase de planejamento. Quando a primeira versão do pipeline estiver implementada, esta seção será atualizada com os comandos reais.

Fluxo pretendido:

```bash
git clone https://github.com/Bonisengna/analistabolsadevalores.git
cd analistabolsadevalores

python -m venv .venv
```

Windows PowerShell:

```powershell
.\.venv\Scripts\Activate.ps1
```

Depois:

```bash
pip install -e .
pytest
```

## Critério de conclusão do MVP

O MVP deve executar um fluxo que:

1. carrega dados;
2. trata e gera features;
3. faz split temporal;
4. treina modelos;
5. avalia as previsões;
6. monta carteira simulada;
7. compara com benchmark;
8. salva métricas e gráficos.

## Status

**Fase atual:** planejamento e reprodução do material de referência.

O planner detalhado do projeto está sendo mantido no Notion.
