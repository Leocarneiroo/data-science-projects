# M35 — Cross Validation: Detecção de Incêndios com Sensores IoT

## Contexto

Aplicação de validação cruzada (cross validation) para avaliar a robustez de um modelo de classificação na previsão de incêndios com base em variáveis ambientais coletadas por sensores IoT. O projeto demonstra como garantir que o modelo generalize bem para dados não vistos.

## Dataset

**smoke_detection_iot.csv** — 62.631 registros

| Variável | Descrição |
|---|---|
| `UTC` | Tempo em segundos UTC |
| `Temperature[C]` | Temperatura do ar (°C) |
| `Humidity[%]` | Umidade do ar (%) |
| `TVOC[ppb]` | Compostos orgânicos voláteis totais |
| `eCO2[ppm]` | Concentração equivalente de CO₂ |
| `Raw H2` | Hidrogênio molecular bruto |
| `Raw Ethanol` | Etanol gasoso bruto |
| `Pressure[hPa]` | Pressão do ar (hPa) |
| `PM1.0` | Material particulado < 1,0 µm |
| `PM2.5` | Material particulado 1,0–2,5 µm |
| `NC0.5` | Concentração numérica < 0,5 µm |
| `NC1.0` | Concentração numérica 0,5–1,0 µm |
| `NC2.5` | Concentração numérica 1,0–2,5 µm |
| `CNT` | Contador de amostras |
| `Fire Alarm` | **Target** — Alarme de incêndio (1 = sim, 0 = não) |

## Escolha do modelo

**Random Forest Classifier** foi escolhido sobre Regressão Logística porque:
- As variáveis ambientais (temperatura, umidade, CO₂, material particulado, etc.) não se relacionam linearmente com a ocorrência de incêndio
- O alerta não depende da variação de apenas um sensor isolado, mas da **combinação de pequenas alterações em vários sensores simultaneamente**
- Random Forest captura interações não-lineares entre features automaticamente

## Pré-processamento

- Renomeação da coluna `Fire Alarm` → `Fire_Alarm` (para evitar problemas com espaço no nome)
- Verificação de tipos de dados
- Verificação de dados faltantes

## Modelo

1. Separação X e y
2. `RandomForestClassifier(n_estimators=100, random_state=42, n_jobs=-1)`
3. **Cross Validation** com `KFold(n_splits=10, shuffle=True, random_state=5)`
4. `cross_val_score` com 10 folds
5. Análise das pontuações por fold e média final

## Avaliação

- Pontuações por fold (10 valores de acurácia)
- Média dos folds como métrica final de robustez

## Stack

```
pandas • scikit-learn (RandomForestClassifier, cross_val_score, KFold)
```