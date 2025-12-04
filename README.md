# Detecção de Fraude em Seguro – Regressão Logística

## Descrição do Projeto
Este projeto utiliza **Regressão Logística** para construir um modelo preditivo capaz de identificar potenciais casos de **fraude em sinistros de seguro**. O foco está em avaliar o desempenho do modelo em um cenário altamente desbalanceado, ajustar o cutoff ótimo e traduzir os resultados em decisões operacionais.

---

## Objetivos
- Realizar análise exploratória do dataset  
- Pré-processar dados (limpeza, tratamento de categorias, criação de dummies)  
- Remover multicolinearidade e preparar features para modelagem  
- Ajustar um modelo de Regressão Logística (statsmodels / sklearn)  
- Determinar cutoff ótimo (Índice de Youden)  
- Avaliar métricas de desempenho e interpretar resultados

---

## Etapas do Projeto
1. **Importação e inspeção dos dados** — checagem de tipos, valores faltantes e proporção de fraude.  
2. **Pré-processamento** — padronização, tratamento de missings, criação de dummies, ordenação de colunas e remoção de colinearidade.  
3. **Modelagem** — ajuste com `statsmodels.Logit` e/ou `sklearn.LogisticRegression`; seleção de variáveis (stepwise) quando aplicável.  
4. **Avaliação de cutoff** — cálculo de ROC/AUC, Youden e escolha do cutoff operacional.  
5. **Validação** — divisão treino/teste, validação do cutoff no conjunto de teste e análise da matriz de confusão.  
6. **Interpretação** — análise de coeficientes, odds ratios e impactos operacionais (falsos positivos e falsos negativos).  
7. **Conclusão e próximos passos** — recomendações para implantação, monitoramento e melhorias.

---

## Resultados Principais (exemplo)
- **Proporção de fraude na base:** ~6%  
- **Cutoff ótimo (Youden):** 0.0341  
- **Sensitividade (Recall):** ~94.8%  
- **Especificidade:** ~57.8%  
- **Acurácia (conjunto de teste):** ~66%  
- **AUC (ROC):** ~0.84  
- **Coeficiente de Gini:** ~0.68

> **Observação:** O cutoff foi selecionado priorizando sensibilidade (detecção de fraudes). Isso aumenta o número de falsos positivos, gerando mais alertas para revisão manual — comportamento esperado em aplicações de prevenção a fraude, onde o custo de não detectar uma fraude costuma ser maior que o custo de investigar um falso positivo.

---

## Recomendações Operacionais
- Priorizar o **top N%** de scores para investigação manual conforme capacidade do time.  
- Monitorar **precision** ao longo do tempo e recalibrar cutoff periodicamente.  
- Em produção, avaliar estratégias de balanceamento (class_weight, SMOTE) e modelos ensemble (XGBoost, LightGBM).  
- Construir dashboard com métricas de performance (AUC, recall por faixa, taxa de falsos positivos, volume de alertas).

---

## Principais Bibliotecas Utilizadas

```bash
pandas
numpy
matplotlib
seaborn
statsmodels
scikit-learn
imblearn
statstests
```

---

## Como rodar (exemplo rápido)
1. Criar ambiente Python e instalar dependências:
```bash
pip install -r requirements.txt
```
2. Abrir o notebook `insurance_fraud_logistic_regression.ipynb`.  
3. Executar sequencialmente as células: pré-processamento → modelagem → avaliação.  
4. Ajustar `cutoff` conforme objetivo operacional.

---

## Contato
E-mail: **thiago.a.v.souza@gmail.com**  
LinkedIn: **https://www.linkedin.com/in/thiagoavsouza/**

