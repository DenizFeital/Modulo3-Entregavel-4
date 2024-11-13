<!-- Sobre este projeto -->
## Sobre este projeto

Para essa atividade, foi feita a análise de uma base de dados com informações de condições de solo e temperatura, relacionadas com o tipo de produto agrícola. Além da análise da base (visto no capítulo 13), você deverá construir alguns modelos preditivos e compará-los em termos da sua performance (abordado no capítulo 14).

Base de dados:

N: quantidade de nitrogênio no solo;
P: quantidade de fósforo no solo;
K: quantidade de potássio no solo;
temperature: temperatura média da região em graus Celsius;
humidity: umidade média do ar na região;
pH: pH do solo;
rainfall: precipitação em milímetros;
label: tipo de cultura plantada nas condições daquela linha.

### Ferramentas utilizadas

As ferramentas utilizadas para este engajamento foram:
* Visual Studio Code
* Plataforma Github
* Jupyter Notebook

<!-- Visão Geral -->
## Visão Geral

### Requisitos

* Fazer uma análise exploratória na base para se familiarizar com os dados;
* Fazer uma análise descritiva narrando os principais achados da base;

### Manuseio das informações:

O manuseio das informações na base de dados é feito através do código Python utilizando uma variedade de bibliotecas. Este código foi também "importado" dentro do Jypter, o que gerou um arquivo com a extensão jpynb.

## Componentes
Os seguintes componentes foram considerados neste arquitura inicial:

## Resultados

        N   P   K  temperature   humidity        ph    rainfall label
    0  90  42  43    20.879744  82.002744  6.502985  202.935536  rice
    1  85  58  41    21.770462  80.319644  7.038096  226.655537  rice
    2  60  55  44    23.004459  82.320763  7.840207  263.964248  rice
    3  74  35  40    26.491096  80.158363  6.980401  242.864034  rice
    4  78  42  42    20.130175  81.604873  7.628473  262.717340  rice
    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 2200 entries, 0 to 2199
    Data columns (total 8 columns):
     #   Column       Non-Null Count  Dtype  
    ---  ------       --------------  -----  
     0   N            2200 non-null   int64  
     1   P            2200 non-null   int64  
     2   K            2200 non-null   int64  
     3   temperature  2200 non-null   float64
     4   humidity     2200 non-null   float64
     5   ph           2200 non-null   float64
     6   rainfall     2200 non-null   float64
     7   label        2200 non-null   object 
    dtypes: float64(4), int64(3), object(1)
    memory usage: 137.6+ KB
    Número de dados duplicados: 0
    
![output_0_1](https://github.com/user-attachments/assets/884f7f75-15ab-46d7-90fd-279dfe8a2c3e)

No gráfico acima percebemos claramente que o item "rainfall" é um outlier. Honestamente, analisando visualmente os dados, eles são bem diferentes mesmo. Porém tenho dúvidas se o meu código não foi preparado corretamente para tais dados.

![output_0_2](https://github.com/user-attachments/assets/59871e2d-ddbd-43b9-90a8-463338497c87)

No gráfico acima percebemos que a distribuição é bem homogenea. Uma análise mais aprofundada talvez possa indicar que o gráfico não está sendo suficientemente detalhado para tal análise. Mas para este exercício podemos aceitar este resultado.

![output_0_3](https://github.com/user-attachments/assets/53069eb4-a53e-441b-abea-7c1fc475ae50)

Neste gráfico também percebemos que existe uma matriz de correlação próxima do 1 (diagonal o que é um bom resultado em relação aos dados apresentados.

    
Foram executados alguns testes utilizando metodologias diferentes, conforme abaixo demonstrado. No final comentarei todos eles em conjunto.

    **Acurácia Regressão Logística: 0.7909090909090909**
                  precision    recall  f1-score   support
    
               0       0.96      0.96      0.96        23
               1       1.00      1.00      1.00        21
               2       0.59      0.80      0.68        20
               3       1.00      1.00      1.00        26
               4       1.00      0.96      0.98        27
               5       0.77      1.00      0.87        17
               6       0.74      1.00      0.85        17
               7       0.93      0.93      0.93        14
               8       1.00      0.43      0.61        23
               9       0.68      0.75      0.71        20
              10       0.42      0.91      0.57        11
              11       1.00      0.71      0.83        21
              12       0.86      0.95      0.90        19
              13       0.00      0.00      0.00        24
              14       0.49      0.89      0.63        19
              15       0.94      1.00      0.97        17
              16       0.80      0.57      0.67        14
              17       1.00      0.43      0.61        23
              18       0.69      0.48      0.56        23
              19       0.85      1.00      0.92        23
              20       0.56      0.95      0.71        19
              21       1.00      0.95      0.97        19
    
        accuracy                           0.79       440
       macro avg       0.79      0.80      0.77       440
    weighted avg       0.79      0.79      0.77       440
    
    **Acurácia KNN: 0.9090909090909091**
                  precision    recall  f1-score   support
    
               0       1.00      1.00      1.00        23
               1       1.00      1.00      1.00        21
               2       0.78      0.90      0.84        20
               3       1.00      1.00      1.00        26
               4       1.00      1.00      1.00        27
               5       1.00      1.00      1.00        17
               6       0.85      1.00      0.92        17
               7       1.00      1.00      1.00        14
               8       0.77      1.00      0.87        23
               9       0.71      0.75      0.73        20
              10       0.65      1.00      0.79        11
              11       1.00      0.86      0.92        21
              12       0.95      1.00      0.97        19
              13       0.93      0.58      0.72        24
              14       0.67      0.95      0.78        19
              15       1.00      1.00      1.00        17
              16       1.00      0.93      0.96        14
              17       1.00      0.83      0.90        23
              18       0.93      0.61      0.74        23
              19       1.00      1.00      1.00        23
              20       0.93      0.74      0.82        19
              21       1.00      1.00      1.00        19
    
        accuracy                           0.91       440
       macro avg       0.92      0.92      0.91       440
    weighted avg       0.92      0.91      0.91       440
    
    **Acurácia SVM (RBF): 0.8113636363636364**
                  precision    recall  f1-score   support
    
               0       0.92      1.00      0.96        23
               1       1.00      1.00      1.00        21
               2       0.61      0.85      0.71        20
               3       1.00      1.00      1.00        26
               4       1.00      0.81      0.90        27
               5       0.89      1.00      0.94        17
               6       0.85      1.00      0.92        17
               7       1.00      0.86      0.92        14
               8       0.79      0.96      0.86        23
               9       0.62      0.75      0.68        20
              10       0.47      0.73      0.57        11
              11       1.00      0.86      0.92        21
              12       0.86      1.00      0.93        19
              13       0.00      0.00      0.00        24
              14       0.44      1.00      0.61        19
              15       1.00      1.00      1.00        17
              16       0.58      0.50      0.54        14
              17       1.00      0.61      0.76        23
              18       0.73      0.35      0.47        23
              19       0.85      1.00      0.92        23
              20       0.87      0.68      0.76        19
              21       1.00      1.00      1.00        19
    
        accuracy                           0.81       440
       macro avg       0.79      0.82      0.79       440
    weighted avg       0.80      0.81      0.79       440
    
    **Acurácia SVM (Polinomial): 0.43863636363636366**
                  precision    recall  f1-score   support
    
               0       0.96      1.00      0.98        23
               1       1.00      0.90      0.95        21
               2       0.57      0.40      0.47        20
               3       0.00      0.00      0.00        26
               4       1.00      0.22      0.36        27
               5       0.87      0.76      0.81        17
               6       1.00      0.59      0.74        17
               7       1.00      0.93      0.96        14
               8       0.55      0.70      0.62        23
               9       0.00      0.00      0.00        20
              10       0.06      1.00      0.11        11
              11       0.42      0.48      0.44        21
              12       0.75      0.32      0.44        19
              13       0.00      0.00      0.00        24
              14       0.00      0.00      0.00        19
              15       1.00      0.82      0.90        17
              16       0.05      0.07      0.06        14
              17       0.90      0.39      0.55        23
              18       1.00      0.26      0.41        23
              19       0.00      0.00      0.00        23
              20       0.90      0.47      0.62        19
              21       0.86      1.00      0.93        19
    
        accuracy                           0.44       440
       macro avg       0.59      0.47      0.47       440
    weighted avg       0.59      0.44      0.46       440
    
    **Acurácia SVM (Linear): 0.85**
                  precision    recall  f1-score   support
    
               0       0.96      1.00      0.98        23
               1       1.00      1.00      1.00        21
               2       0.63      0.85      0.72        20
               3       1.00      1.00      1.00        26
               4       1.00      0.93      0.96        27
               5       0.89      1.00      0.94        17
               6       0.85      1.00      0.92        17
               7       1.00      0.93      0.96        14
               8       0.79      0.83      0.81        23
               9       0.74      0.70      0.72        20
              10       0.53      0.82      0.64        11
              11       1.00      0.86      0.92        21
              12       0.90      1.00      0.95        19
              13       0.67      0.33      0.44        24
              14       0.50      0.79      0.61        19
              15       1.00      1.00      1.00        17
              16       0.82      0.64      0.72        14
              17       0.90      0.78      0.84        23
              18       0.87      0.57      0.68        23
              19       0.88      1.00      0.94        23
              20       0.88      0.74      0.80        19
              21       1.00      1.00      1.00        19
    
        accuracy                           0.85       440
       macro avg       0.85      0.85      0.84       440
    weighted avg       0.86      0.85      0.85       440
    
    **Acurácia Decision Tree: 0.9386363636363636**
                  precision    recall  f1-score   support
    
               0       1.00      1.00      1.00        23
               1       1.00      1.00      1.00        21
               2       1.00      0.90      0.95        20
               3       1.00      1.00      1.00        26
               4       1.00      0.96      0.98        27
               5       0.89      1.00      0.94        17
               6       0.94      1.00      0.97        17
               7       1.00      1.00      1.00        14
               8       0.86      0.83      0.84        23
               9       0.81      0.85      0.83        20
              10       1.00      0.82      0.90        11
              11       1.00      0.95      0.98        21
              12       0.94      0.89      0.92        19
              13       0.75      0.88      0.81        24
              14       0.85      0.89      0.87        19
              15       1.00      1.00      1.00        17
              16       1.00      1.00      1.00        14
              17       1.00      1.00      1.00        23
              18       0.83      0.83      0.83        23
              19       1.00      1.00      1.00        23
              20       0.89      0.84      0.86        19
              21       1.00      1.00      1.00        19
    
        accuracy                           0.94       440
       macro avg       0.94      0.94      0.94       440
    weighted avg       0.94      0.94      0.94       440
    
    **Acurácia Random Forest: 0.9545454545454546**
                  precision    recall  f1-score   support
    
               0       1.00      1.00      1.00        23
               1       1.00      1.00      1.00        21
               2       0.90      0.95      0.93        20
               3       1.00      1.00      1.00        26
               4       1.00      1.00      1.00        27
               5       1.00      1.00      1.00        17
               6       0.94      1.00      0.97        17
               7       1.00      1.00      1.00        14
               8       0.88      0.96      0.92        23
               9       0.74      1.00      0.85        20
              10       1.00      1.00      1.00        11
              11       1.00      0.95      0.98        21
              12       1.00      1.00      1.00        19
              13       0.95      0.75      0.84        24
              14       0.78      0.95      0.86        19
              15       1.00      1.00      1.00        17
              16       1.00      1.00      1.00        14
              17       1.00      1.00      1.00        23
              18       1.00      0.70      0.82        23
              19       1.00      1.00      1.00        23
              20       0.94      0.84      0.89        19
              21       1.00      1.00      1.00        19
    
        accuracy                           0.95       440
       macro avg       0.96      0.96      0.96       440
    weighted avg       0.96      0.95      0.95       440



<!-- Resultado Geral -->
## Resultado Geral

**Acurácia Regressão Logística: 0.7909090909090909**

**Acurácia KNN: 0.9090909090909091**

**Acurácia SVM (RBF): 0.8113636363636364**

**Acurácia SVM (Polinomial): 0.43863636363636366**

**Acurácia SVM (Linear): 0.85**

**Acurácia Decision Tree: 0.9386363636363636**

**Acurácia Random Forest: 0.9545454545454546**


Abaixo um resumo de cada um deles:

Regressão Logística (0.79): A Regressão Logística é usada para classificação binária. Neste caso, ela teve uma acurácia moderada de 79%, indicando desempenho razoável.

K-Nearest Neighbors (KNN) (0.91): O KNN classifica dados com base na proximidade com os vizinhos mais próximos. Com uma acurácia de 91%, ele teve um desempenho muito bom.

Support Vector Machine (SVM) com Kernel RBF (0.81): O SVM com kernel RBF é eficaz para dados não lineares. Com 81% de acurácia, ele teve um desempenho bom.

SVM com Kernel Polinomial (0.44): Esse kernel é útil para relações não lineares, mas teve um desempenho baixo com 44% de acurácia.

SVM com Kernel Linear (0.85): O kernel linear no SVM simplifica a decisão, o que funciona bem em problemas lineares. A acurácia de 85% mostra um bom.

Árvore de Decisão (0.94): Este modelo toma decisões baseadas em uma estrutura hierárquica de condições. Com 94% de acurácia, tornando-o um modelo bastante confiável neste conjunto de dados.

Random Forest (0.95): Esse modelo combina várias árvores de decisão para melhorar a precisão. Com uma acurácia de 95%, ele foi o modelo mais preciso, mostrando um excelente desempenho.

Melhor Modelo: O modelo de Random Forest, com 95% de acurácia, apresentou o melhor desempenho geral, sendo o mais eficaz na classificação dos dados para este engajamento.

<!-- ROADMAP -->
## Roadmap
* Refinar a arquitetura, com mais dados para testes.

## Criação:


Deniz Feital Armanhe (RM559439)- <img width="35" alt="image" src="https://github.com/user-attachments/assets/96a043d2-fe26-459e-96aa-577c929759be">
