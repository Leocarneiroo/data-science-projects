## 2026-07-12 00:00 — Decisão
`origin` alinhado com `Leocarneiroo/data-science-projects`. `main` publicado com sucesso no GitHub.

## 2026-07-15 00:00 — Decisão
Inspecionar o projeto `PCA-analise-de-modelos` primeiro para identificar problemas reproduzíveis antes de propor correções.

## 2026-07-15 00:00 — Decisão
Seguir fluxo obrigatório de brainstorming antes de implementar. Primeiro levantar objetivos do notebook e estado atual do projeto `PCA-analise-de-modelos`.

## 2026-07-15 00:10 — Decisão
Na revisão da ETAPA 1, usar o CSV real como fonte de verdade. O enunciado cita colunas ausentes no arquivo; orientar o usuário registrar essa divergência no notebook.

## 2026-07-15 01:12 — Decisão
Commitar o estado atual do estudo com os arquivos novos já presentes no workspace: `PCA-analise-de-modelos/` + `.context-bridge/`. Motivo: preservar progresso antes de continuar depois.

## 2026-07-15 01:15 — Decisão
Publicar `main` no remoto após o snapshot local. Motivo: encerrar o estudo com backup no GitHub e retomar sem risco de perder progresso.

## 2026-07-16 00:00 — Decisão
Na ETAPA 2 do projeto `PCA-analise-de-modelos`, usar `WebPurchases` como variável alvo (`Y`). Motivo: o enunciado fala em prever intenção de compra online e a coluna já está binária (`0/1`), adequada para classificação.

## 2026-07-16 00:10 — Decisão
Não aplicar `PCA.fit_transform` diretamente em `X` bruto. Motivo: o fluxo correto para modelagem é separar treino/teste, codificar categóricas, padronizar com ajuste no treino e só então ajustar o PCA no treino para evitar vazamento e erro de tipos.

## 2026-07-16 00:20 — Decisão
Publicar no GitHub o avanço da ETAPA 2 do notebook `PCA-analise-de-modelos`, incluindo separação de `X`/`Y`, split treino/teste, encoding, padronização e PCA no fluxo correto de modelagem.

## 2026-07-17 17:40 — Decisão
Na revisão da ETAPA 2 do notebook `PCA-analise-de-modelos/Profissao Cientista de Dados M37 Projeto.ipynb`, considerar como válida a versão final do pipeline após `train_test_split`. Motivo: as células anteriores aplicam `StandardScaler` e `PCA` na base inteira e hoje servem apenas como exploração; a sequência correta aparece no fim da etapa.

## 2026-07-17 17:55 — Decisão
Na revisão geral da atividade M37, considerar a ETAPA 2 tecnicamente concluída no notebook salvo. Motivo: há correlação, codificação de categóricas, separação `X`/`Y`, split treino/teste, padronização e checagem do PCA final.

## 2026-07-17 18:10 — Decisão
Considerar a atividade M37 concluída no notebook salvo. Motivo: ETAPA 3 recebeu Regressão Logística e Random Forest; ETAPA 4 recebeu métricas, matrizes de confusão, comparação final e validação cruzada confirmando o Random Forest como melhor modelo (`f1` médio ~0,84 contra ~0,81 da regressão).
