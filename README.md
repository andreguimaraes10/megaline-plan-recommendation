# Recomendação de Planos de Celular — Megaline

## Objetivo
Construir um modelo de classificação binária capaz de recomendar 
automaticamente o plano mais adequado (Smart ou Ultra) para clientes 
da operadora Megaline, com base no comportamento mensal de uso.

## Contexto do Problema
A Megaline identificou que muitos clientes ainda utilizam planos antigos. 
O modelo analisa dados de chamadas, minutos, mensagens e tráfego de 
internet para recomendar a migração para o plano correto.

## Metodologia
1. **Análise exploratória** — estatísticas por plano e balanço de classes
2. **Divisão dos dados** — treino (60%), validação (20%) e teste (20%)
3. **Comparação de modelos** com busca de hiperparâmetros na validação:
   - Árvore de Decisão
   - Random Forest
   - Regressão Logística
4. **Avaliação final** no conjunto de teste com o melhor modelo
5. **Prova de sanidade** com DummyClassifier como baseline

## Resultados
| Modelo | Acurácia (validação) |
|---|---|
| Árvore de Decisão | 0,7854 |
| Random Forest | **0,8087** |
| Regressão Logística | 0,7092 |

O modelo **Random Forest** (`n_estimators=40`, `max_depth=8`) foi 
selecionado, atingindo acurácia de **0,7994** no conjunto de teste, 
acima do mínimo de 0,75 exigido. O baseline (DummyClassifier) 
atingiu apenas 0,6843, confirmando que o modelo está aprendendo 
padrões reais.

## Tecnologias
- Python
- Pandas
- Scikit-learn
