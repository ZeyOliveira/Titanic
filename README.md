# Titanic
[Criado para a competição do Kaggle](https://www.kaggle.com/competitions/titanic/overview) - Aprendizado de máquina a partir do desastre do Titanic.<br>

Histórico dos resultados das submissões podem ser obtidos diretamento no Kaggle:
...

## [Etapa 1: Modelo com tratamento genérico.](https://github.com/ZeyOliveira/Titanic/blob/main/Etapa1.ipynb)
### Nessa primeira etapa foi decidido tratar de maneira simplificada os dados das colunas necessárias para o modelo sem fazer qualquer engenharia de dados. <br>
- Inicialmente visualizamos e fizemos uma rápida invertigação, identificando **valores faltantes**, e o **tipo de valor** presente em cada coluna; tanto na base de **treino** quanto de **teste**.
- Em seguida, utilizamos a média para tratar as colunas numéricas que possuiam valores faltantes. Também foi feita a **remoção das colunas que tinham alta cardinalidade**, pois poderia **afetar negativamente o modelo**.
- Para finalizar, separamos a base de treino e teste, somente com colunas númericas para submete-las ao modelo, já que ele **não aceita colunas categóricas**. Utilizamos **3 algoritmos de classificação**: *Árvore de Decisão*, *KNN*, *Regressão Logística*. <br>
E **três métricas** para avaliar os resultados: *Ácuracia*, *Matrix de Confusão*, *Erro Médio Quadrático*.
- O **score retornado** pelo Kaggle foi: 0.67703.
<img src="https://github.com/ZeyOliveira/Titanic/blob/main/img/resultado1_kaggle.PNG" />
