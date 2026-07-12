# M27 — Previsão de Doenças Cardiovasculares com Regressão Logística

## Contexto

Modelo de classificação binária para prever o risco de doenças cardiovasculares em pacientes, utilizando um dataset real com 10.001 registros contendo idade, gênero, altura, peso, glicose, colesterol, tabagismo, consumo de álcool e atividade física.

## Dataset

**CARDIO_BASE.csv** — 10.001 registros

| Variável | Descrição |
|---|---|
| `age` | Idade do paciente (em dias) |
| `gender` | Gênero (1 = masculino, 2 = feminino) |
| `height` | Altura em cm |
| `weight` | Peso em kg |
| `gluc` | Glicose (1 = normal, 2 = acima, 3 = muito acima) |
| `cholesterol` | Colesterol (1 = normal, 2 = acima, 3 = muito acima) |
| `smoke` | Fumante (1 = sim, 0 = não) |
| `alco` | Consome álcool (1 = sim, 0 = não) |
| `active` | Atividade física (1 = sim, 0 = não) |
| `cardio_disease` | **Target** — Doença cardíaca (1 = sim, 0 = não) |

## Pré-processamento

- Conversão de tipos (`weight` de string para float, trocando vírgula por ponto)
- Cálculo de **IMC** e filtragem de outliers (IMC < 15 ou > 50, que indicam erro de digitação)
- Remoção de registros com altura/peso implausíveis (ex: adulto com 70 cm ou 250 cm)

## Análise exploratória

- **Boxplot** IMC × doença cardíaca (indivíduos com doença têm IMC médio maior)
- **Boxplot** idade × doença cardíaca (indivíduos mais velhos têm mais problemas)
- **Crosstab** colesterol × doença cardíaca
- **Countplot** glicose × doença cardíaca
- **Countplot** tabagismo × doença cardíaca
- **Matriz de correlação** com heatmap

## Modelo

1. **Separação** X e y, com `train_test_split` (80/20)
2. **Padronização** das features com `StandardScaler`
3. **Balanceamento** das classes com `SMOTE` (imblearn)
4. **Regressão Logística** com `LogisticRegression(random_state=0)`
5. Interpretação de coeficientes (`intercept_`, `coef_`)

## Avaliação

- `classification_report` (precision, recall, F1)
- `accuracy_score`
- `roc_curve` e `roc_auc_score` (curva ROC)

## Stack

```
pandas • scikit-learn (LogisticRegression, StandardScaler, train_test_split)
imblearn (SMOTE) • matplotlib • seaborn
```