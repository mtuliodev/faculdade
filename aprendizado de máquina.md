# Aulas anteriores

Definições:
- Um programa aprende a partir da experiência E, em relação a uma classe de tarefas T, medido por desempenho P, seu desempenho nas tarefas T, vai melhorando a cada Experiência E
- Instâncias e atributos
- Atributo de classificação: São colunas que descrevem o resultado do modelo
	Ex: Se eu tenho uma tabela que eu quero saber se tal pessoa vai conseguir sobreviver ou não, a coluna de atributo de classificação vai descrever o resultado
Tipos de problemas:
	- Classificação: Prever um atributo nominal (Se morreu ou não, se irá pertencer a classe A,B,C...)
	- Regressão: Prever um atributo numérico
	- Agrupamento (clusterização): Agrupar as instâncias
		Ex: Identificar tipos de perfis dos meus clientes
	- Associação: Buscar semelhança associações entre os elementos
		Ex: Todo cliente que usa óculos escuro compra o produto 1

# Aula 21-02
- Na árvore de decisão, a raíz da árvore é o atributo mais importante, no qual é a partir dele que eu consigo distinguir os padrões da base
    - Ex: Se para descobrir qual pessoa é de qual cor, e eu percebo que somente pessoas com mais de 30 anos são da cor X e pessoas com menos de 30 são da cor Y, o atributo Idade será a raiz da minha árvore
 - Se tamanho > 78, então Amarelo
 - Se tamanho > 78 = Antecedente / Então amarelo = Conseguinte / Amarelo = Classe
 
- Indução de Regras
  - A partir das regras que existem na base atual, o algoritmo identifica novos testes para identificar um padrão e melhorar a precisão
    - Diretamente: Através da base de dados
      - Ripper
    - Indiretamente: Pela árvore de decisão
  - **Algoritmo zeroR(régua)**:
    - Não cria nenhuma regra
    - Atribui todos os registros a uma classe majoritária
    - Serve como baseline para avaliar a qualidade dos modelos, ou seja, se ele acerta 80%, todos os meus algoritmos mais complexos devem acertar de 80% pra cima
  - **Algoritmo OneR**:
    - Usado para encontrar o atributo mais relevante, a raíz da arvore
    - Seleciono uma coluna de atributo como antecedente, e outra como conseguinte que é a classe. A partir disso, eu faço um filtro por todos os valores distintos da coluna de atributo e todos os valores diferentes que ele atingiu na classe
    - A coluna que tiver menos erros pela classe, é a raíz(atributo mais relevante)
  - **Algoritmo PRISM**:
    - A partir da classe, eu filtro por cada valor distinto dela e tento identificar algum padrão que existe nas outras colunas dentro desse valor distinto
      - Ex: Se na minha classe de risco, no valor alto, todos os valores são mais de 1000, então se o valor é mais de 1000, o meu risco é alto 
  
    
# Aula 28-02

## Árvores de decisão
- Forma indireta de gerar as regras
- Simples e interpretável
- Eu posso usar a árvore para **classificação** e **regressão**
- Atributo raiz/ancestral: é o que melhor classifica/descreve sua base e o que fica no nível 0 da base
- Atributos de cima: os mais importantes
- Para descobrir a quantidade de instâncias por classe: na raiz, a classe que tiver mais instâncias(maioria
- Árvore é um conjunto de noz folha e noz teste
- Nó folha/regra: é onde termina a ramificação da árvore
- Nó teste/nodo: o que possui ramificações abaixo dele
- Altura da folha
- Samples: número total de instâncias
- Esquerda da árvore: verdadeiro / Direita da árvore: Falso
- Árvore muito alta: quer dizer que está muito difícil de descrever os meus dados
- Se a árvore atinge a mesma precisão que um modelo de aprendizado mais complexo, prefira a árvore
- Conjunção: /\
- Disjunção: \/
- Quanto menos nós testes eu tiver, melhor
- Índice GIMI - mede a pureza do atributo
### Entropia
- É o grau de desordem
![image](https://github.com/mtuliodev/faculdade/assets/86724878/bdb7f5a3-0110-46cd-9357-fcb525043859)

- A base de log = quantidade de valores distintos da classe
### Como identificar o atributo raiz?
- Identificar o atributo de entrada que melhor classifica/distingue o atributo de saída
- ID3: ganho(atributo) = entropia(classe/atributo de saída) - entropia(atributo de entrada)
	- O atributo que tiver maior ganho será o raiz

# Aula 13-03
- Atributo dicotômico = atributo binário
- Label Encoder: binariza os dados categóricos ordinais e os dados numéricos
- OneHot Encoder: transforma cada dado nominal distinto não ordinal em colunas, em que se a coluna do dado X é a resposta na linha, ela vira 1

![image](https://github.com/mtuliodev/faculdade/assets/86724878/74ee59e3-54a4-4b0b-a35d-c83adadda284)

Siglas:
	- VP: Verdadeiro positivo
 	- VN: Verdadeiro negativo
	- FP: Falso positivo
 	- FN: Falso negativo
  - FN é o pior de todos
- train_test_split: separa as linhas de entrada entre treino e teste
- accuracy_score:mede a precisão geral do modelo
- precision: O quanto ele acertou na classe X diante de todas as linhas que têm em todas as classes
  - VP/VP + FP
- recall/revocação/sensibilidade: o quanto o modelo acertou naquela classe X dentro de todas as linhas que têm naquela classe
  - VP/VP + FN
- f1 score:
  - 2xPrecisionxRecall/Precision+Recall
- support:
- TVP(Verdadeiro positivo) = recall

- Métricas da árvore:
  - Cobertura por classe: samples/value(qtde de instâncias classificadas/qtd de instâncias da classe na raíz da árvore)	
  - Cobertura global: samples/value(qtde de instâncias classificadas/qtd de instâncias totais na raíz da árvore)

# Aula 20-03

- Ao lidar com uma base, sempre ficar atento a correlação entre os atributos de entrada e saída
  - Se o atributo de entrada for altamente relacionado com o de saída(>0.7), excluir esse atributo da base
- Dado incosistente: Instâncias em que seus dados são exatamente iguais
  - Ex: Ambos João e Carlos, tem 3 anos, cursaram inglês e morreram aos 34 anos
  - Nesse caso eu devo excluir **ambas** instâncias
  - Se eu tiver dados inconsistentes ímpares, devo considerar os dados que foram a maioria
- Técnicas para balancear as classes desbalanceadas:
  - Oversampling: Adicionar instâncias a classe minoritária
    - Aleatório: Busca instâncias aleatórias da classe minoritária até dar o balanceamento 
    - Heurística: "Cria" novas instâncias a partir dos dados já existentes
    - Realizar isso no conjunto de **treino**
  - Undersampling: Remover instâncias da classe majoritária
    - Aleatório: Remove instâncias aleatórias da classe majoritária até dar o balanceamento 
    - Heurístico: "Tentar" deixar os melhores dados da classe majoritária
- A árvore de decisão NÃO aceita dados nulos
  - Para substituir os dados nulos, colocar a moda/mediana do atributo(mas pode gerar inconsistências)
  - KNNinput

# Aula 10-04

## Naive Bayes
- Serve para prever a probabilidade
- Etapas
  	- Fazer a matriz de probabilidade
  	- Classificar a quantidade de registros distintos em razão de todos na classe, e com base na classe, fazer essa razão para os outros atributos(5/13) 

![image](https://github.com/mtuliodev/faculdade/assets/86724878/4e09c7aa-6bf6-47ba-80eb-edf5b2a394b9)

# Aula 17-04

## Matriz de confusão:
- Quando eu rodo ela, não quer dizer que acabou o meu trabalho
- O objetivo principal dela é entender como o modelo classificou a classe em torno das variáveis
- Se o seu modelo deu 97% de acurácia, não quer dizer que ele esteja certo

## Ensemble Learning / Aprendizagem em Conjunto
- Ensembles:
	- Métodos que geram muitos classificadores e combinam os seus resultados
 - O desempenho de um conjunto com vários classificadores fracos é geralmente melhor do que um único classificador, desde que tenha a mesma quantidade de informação de treinamento
- Condições necessárias para ele funcionar:
  	- Ter diversidade: pois os classificadores base devem ser independentes
  	- O desempenho dos classificadores base deve ser melhor que classificação aleatória
- O seu resultado é gerado a partir da combinação de predições de todos os classificadores

## Random Forest
- Não é interpretável
- Faz uma seleção aleatória com reposição de instâncias pra cada árvore(técnica Bootstrap). Ou seja, se eu tenho 10.000 instâncias, ele vai fazer a seleção aleatória 10.000 vezes
- Selecionar a quantidade de atributos para cada árvore(o algoritmo vai sempre selecionar essa quantidade, mas vai ser aleatoriamente).
- Ex: Separo uma parte para treino e teste, e determino a quantidade de árvores que eu quero gerar
- Quando gerar em python, ficar atento ao número de árvores que serão usadas
- Hiperparâmetros mais importantes:
  - Quantidade de árvores
  - Quantidade de atributos

## Bagging
 - Algoritmo no qual eu combino com outro tipo de algoritmo usado como hiperparâmetro
 - Ele é um estimador homogêneo, que combina o mesmo algoritmo várias vezes

## Stacking
 - Estimator: Aplico um algoritmo na base como método de classificação
 - Final_estimator: Após fazer o estimator, eu uso outro algoritmo para classificar os dados em cima do primeiro algoritmo

# Aula 24-04

## Regras de Associação
- O grau de confiança da regra se mede pelo quantidade que tal evento acontece em detrimento de um evento X.
  - Ex: 50% das vezes fizeram evento X depois de já terem feito o evento Y

- Métricas de qualidade:
  - Cobertura
  - Acurácia(confiança)
    - Quantidade de registros que levaram o item A e B / Quantidade de registros que levaram o item A
    - Índice de confiança usado geralmente: 80%
  - Lift(coeficiente de interesse)
    - Quantidade de confiança dos itens A e B / Quantidade de suporte d	o item B
    - Quanto maior o lift, melhor é a regra
 
- Algoritmo apriori
- 1° passo: Estabelecer os suportes de cada itemset
  - Diante da base de dados, eu faço o suporte para cada atributo(itemset1)
    - Ou seja, eu estabeleço quantas vezes tal evento ocorreu
    - Ex de suporte mínimo: 30%
    - Ex de confiança mínima: 80%
    - Se não encontrar nenhuma regra a partir desses indicadores, ir diminuino os parâmetros pouco a pouco
  - Depois, faço o suporte para cada combinação de atributos(itemset2)
    - Se no itemset1 permaneceram os eventos X, Y e Z, eu faço as combinações de XY, YZ e XZ
  - Faço isso sucessivamente estabelendo combinações entre os atributos(itemset3 ou mais)
    - Baseado no exemplo acima, a última combinação seria XYZ
- 2° passo: Estabeleço regras para cada itemset
  - Começar sempre do itemset2
 
# Aula 08-05

- Black box e white box
  - Black box: O modelo gera um resultado a partir de um dataset, mas o usuário final não sabe como que o modelo chegou nesse resultado.
  - White box: O modelo gera o resultado, e o modelo mostra ao usuário como que chegou ao resultado, mostrando os detalhes.	

- OneHotEncoder: Dados não ordinais
- LabelEncoder: Dados ordinais/dados dicotômicos

## Métodos de amostragem
- Holdout: Do total de registros, separar uma parte para treinamento e outra para teste(train_test_split)
- Cross-validation:
  - Treino -> Validação -> Teste
  - Dos que sobraram do train_test_split, eu faço o cross validation nela
  - Insiro um valor K, que será em quantas partes eu vou dividir

# Projeto 1
- Etapa 1: Selecionar os atributos/instâncias(incluir as pessoas que não foram diagnosticadas com DRC para balanceamento)
- Etapa 2: Codificar os atributos pra numérico(Label Encoder, One Hot e Ordinal Encoder)
- Etapa 3: Correlação dos atributos de entrada e saída
- Etapa 4: Entender a redundância da base
- Etapa 5: Definir o balanceamento do atributo de saída
- **Árvores de decisão, ZeroR, Random Forest, CNN, Bagging + Random Forest**
