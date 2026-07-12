# EBAC — Profissão Cientista de Dados

Repositório com os projetos práticos mais relevantes desenvolvidos durante o curso **Profissão Cientista de Dados** da EBAC, cobrindo machine learning supervisionado e não supervisionado, validação de modelos, SQL e visualização de dados.

## Projetos

| Módulo | Tema | Algoritmo | Dataset | Registros | Pasta |
|---|---|---|---|---|---|
| M27 | Previsão de Doenças Cardiovasculares | Regressão Logística + SMOTE | CARDIO_BASE | 10.001 | [`M27-regressao-logistica-cardio/`](./M27-regressao-logistica-cardio) |
| M28 | Duelo de Modelos (Titanic) | Árvore de Decisão vs Reg. Logística | Titanic | 891 | [`M28-duelo-modelos-titanic/`](./M28-duelo-modelos-titanic) |
| M32 | Classificação de Vinhos | Random Forest (Classificação + Regressão) | Wine Quality | 1.600 | [`M32-random-forest-wine/`](./M32-random-forest-wine) |
| M35 | Detecção de Incêndios via IoT | Cross Validation (KFold 10) + Random Forest | Smoke Detection IoT | 62.631 | [`M35-cross-validation-iot/`](./M35-cross-validation-iot) |

## Skills demonstradas

- **Pré-processamento:** Encoding (Label + One-Hot), SMOTE, StandardScaler, tratamento de outliers (IQR), dados faltantes
- **ML supervisionado:** Regressão Logística, Árvore de Decisão, Random Forest (classificação e regressão), Naive Bayes
- **Validação:** Cross Validation (KFold 5/10), GridSearchCV, RandomizedSearchCV
- **Métricas:** ROC/AUC, classification report, matriz de confusão, R², MSE, MAE
- **Regularização:** Lasso (L1), Ridge (L2), ElasticNet
- **SQL:** SELECT, JOIN, DDL (CREATE/INSERT), agregações
- **Visualização:** matplotlib, seaborn, plotly (11 tipos de gráficos)

## Stack

```
Python 3 • pandas • numpy • scikit-learn • imblearn • scipy
matplotlib • seaborn • plotly • sqlite3
```

## Como executar

```bash
# Clonar o repositório
git clone https://github.com/Leocarneiroo/ebac-data-science-projetos.git
cd ebac-data-science-projetos

# Instalar dependências
pip install pandas numpy scikit-learn imblearn scipy matplotlib seaborn plotly

# Abrir qualquer notebook
jupyter notebook M27-regressao-logistica-cardio/notebook.ipynb
```

Cada pasta contém o notebook + dataset correspondente, prontos para execução.

## Sobre

Desenvolvido como parte do curso Profissão Cientista de Dados da EBAC (Módulos 13 a 36).