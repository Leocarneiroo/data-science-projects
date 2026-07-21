# EBAC - Profissao Cientista de Dados

Repositorio com projetos praticos desenvolvidos durante o curso **Profissao Cientista de Dados** da EBAC, cobrindo pre-processamento, modelos supervisionados, validacao e comparacao de algoritmos.

## Projetos

| Modulo | Tema | Algoritmo | Dataset | Registros | Pasta |
|---|---|---|---|---:|---|
| M27 | Previsao de doencas cardiovasculares | Regressao Logistica + SMOTE | CARDIO_BASE | 10.001 | [`M27-regressao-logistica-cardio/`](./M27-regressao-logistica-cardio) |
| M28 | Duelo de modelos no Titanic | Arvore de Decisao vs Regressao Logistica | Titanic | 891 | [`M28-duelo-modelos-titanic/`](./M28-duelo-modelos-titanic) |
| M32 | Classificacao de vinhos | Random Forest | Wine Quality | 1.600 | [`M32-random-forest-wine/`](./M32-random-forest-wine) |
| M35 | Deteccao de incendios via IoT | Cross Validation + Random Forest | Smoke Detection IoT | 62.631 | [`M35-cross-validation-iot/`](./M35-cross-validation-iot) |
| M37 | Analise de clientes e PCA | PCA + modelos de classificacao | Marketing Campaign | 2.240 | [`PCA-analise-de-modelos/`](./PCA-analise-de-modelos) |
| M39 | Propensao de compra de carros | XGBoost | CARRO_CLIENTES | 1.000 | [`XGBoost/`](./XGBoost) |
| M40 | Propensao de compra de carros | SVM linear vs SVM poly | CARRO_CLIENTES | 1.000 | [`SVM/`](./SVM) |

## Destaques

- Pre-processamento: Label Encoder, One-Hot Encoding, SMOTE, StandardScaler e tratamento de dados faltantes.
- Modelagem: Regressao Logistica, Arvore de Decisao, Random Forest, PCA, XGBoost e SVM.
- Validacao: train/test split, matriz de confusao, classification report, acuracia, precision, recall, f1-score e cross-validation.
- Comparacao recente: no dataset `CARRO_CLIENTES`, XGBoost teve melhor desempenho que SVM linear e SVM poly.

## Tecnologias

```text
Python 3
pandas
numpy
scikit-learn
imbalanced-learn
scipy
matplotlib
seaborn
plotly
jupyter
```

## Como executar

```bash
git clone https://github.com/Leocarneiroo/data-science-projects.git
cd data-science-projects
pip install -r requirements.txt
jupyter notebook
```

Cada pasta contem o notebook e o dataset correspondente.
