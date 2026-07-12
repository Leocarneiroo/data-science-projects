# M28 — Duelo de Modelos: Árvore de Decisão vs Regressão Logística

## Contexto

Comparação lado-a-lado de dois algoritmos de classificação para prever a sobrevivência de passageiros no Titanic. O projeto avalia qual modelo performa melhor quando submetidos ao mesmo pipeline de pré-processamento e otimização de hiperparâmetros.

## Dataset

**Titanic** (train.csv + test.csv) — 891 registros de treino

| Variável | Descrição |
|---|---|
| `Survived` | **Target** — Sobrevivência (0 = não, 1 = sim) |
| `Pclass` | Classe do bilhete (1, 2, 3) |
| `Sex` | Gênero |
| `Age` | Idade |
| `Fare` | Preço do bilhete |
| `Embarked` | Porto de embarque (C, Q, S) |
| `Cabin` | Número da cabine |
| `Name`, `Ticket` | Removidos (irrelevantes para o modelo) |

## Pré-processamento

- Preenchimento de nulos: `Age` e `Fare` com a média
- **Label Encoding:** `Sex` (male = 0, female = 1)
- **One-Hot Encoding:** `Embarked` com `pd.get_dummies`
- **Feature engineering:** `Cabin_known` (1 = tem cabine registrada, 0 = não)
- Remoção de colunas irrelevantes (`Name`, `Ticket`, `Cabin`)

## Modelos

### Modelo 1: Regressão Logística
- `LogisticRegression(random_state=42)`
- Otimização com `GridSearchCV`

### Modelo 2: Árvore de Decisão
- `DecisionTreeClassifier(random_state=42)`
- Otimização com `GridSearchCV`

### Pipeline comum (ambos os modelos)
- `StandardScaler` para padronização
- `SMOTE` para balanceamento de classes
- Matriz de correlação para seleção de features

## Avaliação

- `classification_report` (precision, recall, F1)
- `accuracy_score`
- `roc_curve` e `roc_auc_score` (curva ROC)
- `confusion_matrix`

## Pontos fortes e fracos (análise comparativa)

| Critério | Árvore de Decisão | Regressão Logística |
|---|---|---|
| Interpretabilidade | Alta (regras visíveis) | Média (coeficientes) |
| Overfitting | Mais suscetível | Mais robusta |
| Não-linearidade | Captura naturalmente | Não captura sem feature engineering |
| Velocidade | Rápida | Muito rápida |

## Stack

```
pandas • numpy • scikit-learn (LogisticRegression, DecisionTreeClassifier, GridSearchCV)
imblearn (SMOTE) • sklearn.preprocessing (StandardScaler)
matplotlib • seaborn
```