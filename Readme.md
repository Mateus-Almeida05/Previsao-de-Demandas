## **Previsão de Demandas**

## **1\. Introdução**

Este projeto tem como objetivo desenvolver, testar e comparar modelos de previsão de demanda para uma rede de lojas, avaliando não apenas a precisão estatística das previsões, mas também o impacto financeiro de cada abordagem. O trabalho abrange todas as etapas do ciclo de ciência de dados — desde o entendimento dos dados até a análise de custos decorrentes de erros de previsão — com foco em apoiar decisões estratégicas de abastecimento e reduzir custos operacionais.

## **2\. Problema Resolvido**

O desafio central consiste em prever a demanda futura de produtos com o máximo de precisão possível, a fim de minimizar dois tipos de perdas financeiras:

* Custo de estoque – quando a previsão é maior que a demanda real, gerando excesso de produtos armazenados.

* Custo de oportunidade – quando a previsão é menor que a demanda real, ocasionando falta de produtos e perda de vendas.

O objetivo é identificar o modelo que melhor equilibra acurácia preditiva e impacto financeiro para diferentes lojas e famílias de produtos.

## **3.1. Modo de Resolução**

O projeto foi dividido em quatro etapas:

3.1. Entendimento e Preparação dos Dados

* Análise exploratória para identificar padrões de venda, sazonalidades e outliers.

  * Enriquecimento da base com variáveis externas (ex.: preço do petróleo, feriados, promoções).

  * Criação de *features* temporais e lags de vendas para capturar tendências históricas.

3.2. Modelagem e Treinamento

* Avaliação do modelo vigente (baseline).

  * Treinamento e comparação de diversos algoritmos: Regressão Linear, LightGBM, CatBoost, Gradient Boosting, XGBoost e LSTM.

  * Otimização de hiperparâmetros com Optuna.

  * Desenvolvimento de modelos único (global) e segmentados por loja.

3.3. Segmentação de Modelos

* Criação de pipelines independentes para lojas com comportamento distinto.

  * Comparação entre o modelo global e os segmentados em termos de erro e estabilidade.

3.4. Avaliação Financeira

* Cálculo dos custos de estoque e oportunidade com base nas previsões.

  * Comparação dos modelos considerando o custo total e as métricas de erro (MAE e RMSE).

## **4\. Estrutura do Projeto**

Projeto\_Previsao\_Demandas  
├── 01\_entendimento\_dados.py         \# Análise exploratória e preparação das bases  
├── 02\_modelagem.py                  \# Treinamento e comparação de modelos  
├── segmentacao\_de\_modelos.py        \# Desenvolvimento de modelos por loja  
├── avaliacao\_financeira.py          \# Cálculo de custos e comparação financeira  
├── dados/                           \# Bases de treino, validação e custos  
└── modelos/                         \# Pipelines salvos (.pkl)

## **5\. Tecnologias Utilizadas**

* Linguagem: Python

* Bibliotecas Principais:

  * Manipulação de dados: pandas, numpy

  * Visualização: matplotlib, seaborn

  * Modelagem: scikit-learn, lightgbm, catboost, xgboost, tensorflow

  * Otimização de hiperparâmetros: optuna

  * Serialização de modelos: joblib

## **6\. Resultados Obtidos** 

O modelo desenvolvido apresentou o melhor equilíbrio entre acurácia e custo financeiro, reduzindo em mais de 90% o custo total em comparação ao modelo vigente. Os modelos segmentados mostraram desempenho semelhante em precisão, mas com custo um pouco superior.

| Modelo | MAE | RMSE | Custo Total (R$) |
| :---: | :---: | :---: | :---: |
| Vigente | 3.287 | 10.898 | 626.804.845,55 |
| Único (CatBoost) | 471 | 1.278 | 36.259.814,83 |
| Segmentado | 517 | 1.237 | 43.274.465,63 |

## **7\. Conclusão**

O projeto demonstrou que a aplicação de técnicas avançadas de análise de dados e aprendizado de máquina, aliadas a uma abordagem financeira estruturada, é capaz de otimizar de forma significativa o processo de previsão de demanda. A integração entre análise estatística, engenharia de atributos e mensuração de custos permitiu não apenas aprimorar a precisão das previsões, mas também compreender o impacto econômico de cada decisão tomada pelos modelos. Com isso, foi possível transformar a análise preditiva em uma ferramenta estratégica, que orienta o planejamento de estoques e o abastecimento de lojas de forma mais eficiente e alinhada à realidade do negócio. Além de reduzir custos operacionais e perdas decorrentes de excesso ou falta de produtos, o projeto também fornece uma base sólida para decisões futuras, mostrando como a inteligência de dados pode contribuir diretamente para a rentabilidade e a sustentabilidade das operações.

