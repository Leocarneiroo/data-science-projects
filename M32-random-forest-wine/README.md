# M32 — Random Forest: Classificação de Vinhos

## Contexto

Classificação multi-classe da qualidade de vinhos tintos com base em características químicas, utilizando Random Forest. O projeto também cobre Random Forest para regressão no mesmo dataset.

## Dataset

**winequality-red.csv** — 1.600 registros

| Variável | Descrição |
|---|---|
| `fixed acidity` | Acidez fixa |
| `volatile acidity` | Acidez volátil |
| `citric acid` | Ácido cítrico |
| `residual sugar` | Açúcar residual |
| `chlorides` | Cloretos |
| `free sulfur dioxide` | SO₂ livre |
| `total sulfur dioxide` | SO₂ total |
| `density` | Densidade |
| `pH` | Nível de pH |
| `sulphates` | Sulfatos |
| `alcohol` | Teor alcoólico |
| `quality` | **Target** — Pontuação de 0 a 10 |

## Pré-processamento

- Verificação de tipos e dados faltantes
- Análise de outliers com `describe()` e método **IQR** (identificados 55 outliers em `total_sulfur_dioxide`, mantidos pois são estatísticos, não erros)
- Verificação de balanceamento da variável target
- **Matriz de correlação** e seleção de features mais relevantes

## Modelos

### 1. Random Forest — Classificação
- `RandomForestClassifier(n_estimators=100, random_state=42)`
- Otimização com `RandomizedSearchCV`
- Validação com `StratifiedKFold`
- Balanceamento com `RandomOverSampler` (imblearn)
- Pipeline integrado com `imblearn.pipeline.Pipeline`

### 2. Random Forest — Regressão
- `RandomForestRegressor`
- Otimização com `RandomizedSearchCV`
- Métricas: `r2_score`, `mean_squared_error`, `mean_absolute_error`

## Avaliação

- `accuracy_score`, `classification_report`, `confusion_matrix`
- `r2_score`, `mean_squared_error`, `mean_absolute_error` (regressão)

## Stack

```
pandas • scikit-learn (RandomForestClassifier, RandomForestRegressor, RandomizedSearchCV, StratifiedKFold)
imblearn (RandomOverSampler, Pipeline)
matplotlib • seaborn
```