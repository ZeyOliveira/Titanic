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

<br>

## [Etapa 2: Data Cleaning e Tratando Colunas Categóricas.](https://github.com/ZeyOliveira/Titanic/blob/main/Etapa2.ipynb)
### Nesse ponto foi decidido fazer o tratamento dos valores vazios e das colunas de texto. <br>
- Inicialmente focamos na coluna que tinha menos valores vazios (Embarked), e utilizando-se do "entendimento do negócio" fizemos o tratamento usando dados reais.
- Depois, tratamos os valores vazios da coluna (Age) fazendo o uso da própria base analisando os recursos. E o mesmo foi feito para a base de teste.
- Removemos colunas com alta cardinalidade e que aparentemente não iriam contribuir em nada para prever a variável **target**.
- Para tratar colunas de texto, foi utilizado o **OneHotEncoder** do sklearn e uma **função lambda** com um **if-ternário**.
- Utilizamos em seguida, os mesmos modelos e métricas de avaliações vistas anteriormente.
- - O **score do** Kaggle foi: 0.76315.
<img src="https://github.com/ZeyOliveira/Titanic/blob/main/img/titanic_resultado2.PNG" />

<br>

## [Etapa 3: Tratando Escalas, Criando novas Features e Entendendo o Negócio.](https://github.com/ZeyOliveira/Titanic/blob/main/Etapa3.ipynb)
### Na etapa 3 entendemos melhor o négocio consultando a documentação da competição, e tentando melhorar os resultados. <br>
- Foi feito o tratamento da escala dos dados das colunas **Age** e **Fare**.
- Aprofundamos nas colunas **SibSp** e **Parch**. Apartir delas foi criada uma nova feature chamada **Familiares**.
- Verificamos a correlação entre as variáveis e selecionamos as melhores.
- O primeiro resultado foi:
<img src='https://github.com/ZeyOliveira/Titanic/blob/main/img/resultado_e3.PNG' />

<br>

- Em seguida, fizemos uma alteração simples no **estado aleatório** (random_state) do **train_test_split, de 1 para 42.**
- O segundo resultado foi:
<img src='https://github.com/ZeyOliveira/Titanic/blob/main/img/resultado_e3_1.PNG' />

<br>

## [Etapa 4: Selecionando novos modelos para fazer a previsão dos dados.](https://github.com/ZeyOliveira/Titanic/blob/main/Etapa4.ipynb)
### Foi utilizada as bases com os tratamento realizados na **Etapa 3**. <br>
- Foi selecionado novos algoritmos para fazer a previsão dos dados: *Regressão Logística*, *Random Forest*, *Support Vector Machines*.
- Dessa vez um modelo não visto obteve **resultado superior** ao modelo de Regressão Logística, o **SVC** do submódulo **SVM**.
- O **score retornado** pelo Kaggle foi: 0.78229.
<img src='https://github.com/ZeyOliveira/Titanic/blob/main/img/resultado_e4.PNG' />
