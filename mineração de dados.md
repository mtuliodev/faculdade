# Aulas anteriores

- KDD – Knowledge Discovery in Database
- KDD → Tem o objetivo de descoberta organizada de padrões e descoberta de conhecimento útil e não óbvio sustentado por mecanismos/algoritmos computacionais
  - 1° significado de KDD = Seleção + Preparação + Transformação + Algoritmo (Data Mining) + Interpretação
  - 2° significado de KDD 
    - Entendimento do Negócio: Entender o objetivo do projeto e as expectativas para o negócio
    - Entendimento dos dados: Montagem/captura da base de dados e análise/exploração dos dados
## Preparação dos dados
- Modelagem do problema: Aplicação de técnicas de Aprendizado de máquina
- Avaliação do modelo: Avaliação/teste do modelo
- Implantação: Conhecimento adquirido pelo modelo e apresentado de uma forma que o cliente consiga utilizar no seu negócio
	- Ciência Básica: tem o dever de propor teorias para explicar fenômenos(gera teorias)
	- Ciência Experimental: usa hipóteses/experimentos através da estatística descritiva/inferencial para comprovar que a hipótese está certa ou errada(gera observações válidas)
	- Ciência por dados: conhecimento útil e não óbvio(gera modelos computacionais)
- IA: Algoritmo computacional que quando em operação aparentam ter comportamento inteligente quando comparados ao ser humano
- Big Data: 
    - Volume
    - Variedade (diferentes tipos de dados) 
    - Velocidade (grande fluxo)
- Data Science:
	  🡪 Geração
	  🡪 Captura
	  🡪 Armazenamento
	  🡪 Manipulação
	  🡪 Data Analytics
	  🡪 BI
	  🡪 Descoberta de padrões
	  🡪 Aplicabilidade do dado

- Machine Learning: Campo de estudo que permite aos computadores aprender sem serem explicitamente programados
- Data Mining: Extrair padrões
- Conhecimento explícito - representado por documentos, procedimentos, relatórios e bases de dados(redundante e incompleto, sem informação, dado cru)
- Conhecimento **tácito** - O que é descoberto a partir dos dados, a descoberta do conhecimento
- Ciência de dados: gera hipóteses
- Estatística: inicia seu trabalho a partir das hipóteses

- Problema de indução | Cisne Negro (Hume)

# Aula 05-03

## Processo KDD - Detalhamento
- Modelagem do domínio do problema
- Montagem da base de dados
- Enriquecimento/melhoramento da base
- Limpeza de dados
- Análise dos outliers
- Codificação
- Data Mining
- Validação de padrões
- Apresentação do conhecimento

## Metodologias de KDD
- CRISP-DM: bom, mas é padrão. Um excel melhorado
- SEMMA: mais estatístico


# Aula 21-03
- Nos meus modelos de inferência, devo estar atento as features.
- Se minha base tem somente fatos, meu modelo vai gerar dados óbvios
- Se minha base tem somente julgamentos, meu modelo vai gerar dados aleatórios
- Minha base deve conter fatos e julgamentos, para que haja um modelo representativo e não polarizado


# Aula 02-04 - Dados ausentes

- Entropia: mede o grau de confusão/caos do atributo/informação
- Entropia mínima: Informação baixa
- Probabilidade gera informação, informação gera entropia e entropia gera ganho de informação
## Valor ausente x valor vazio
- Valor ausente: É aquele valor que não foi indserido no conjunto, mas que seu valor existe
- Valor vazio: É aquele valor que não se pode supor nenhum valor a partir dele
- Se a técnica de Data mining se baseia na probabilidade, ela consegue lidar com valores ausentes
  	- Porém, essa técnica não funciona com bases com dados massivos em massa

## Tratamento dos dados ausentes
- Fazer uma análise e decidir se vai eliminar ou não o atributo/registro que contém dado ausente
- Recuperar o dado ausente
- Técnicas de Data Mining que lidam com valores ausentes, porém em diferentes graus

## Mecanismos de dados ausentes
- MCAR: os valores ausentes estão distribuidos aleatoriamente, em que a probabilidade de encontrar um valor ausente é a mesma para qualquer valor do atributo
  - Inputar os valores ausentes pela média não é uma boa ideia, pois altera a variância do atributo
- MAR: valores ausentes, mas que estão ausentes pela relação entre duas variáveis. Ex: Pessoas com ensino superior completo não falam a sua idade
  - O correto deveria ser inputar a média. Ou seja, somente fazer a média de idade para as pessoas com ensino superior
 
## Técnicas para lidar com dados ausentes
- Regressão linear: Quando a base é linear, faço a correlação entre as duas bases para inputar os dados ausentes para a coluna
- Redes neurais: Quando a base é complexa e não linear, faço a correlação entre as duas bases para inputar os dados ausentes para a coluna

# Aula 09-04

- Efeito borboleta: pequenos movimentos que geram grandes catástrofes

## Correlação
- Se a correlação entre as duas colunas de causa for maior que 0.8, eu elimino uma das duas.
- Se a correlação entre as colunas de causa e efeito for grande, e elas forem numéricas, eu devo manter elas. Caso sejam categóricas, eu removo.
- Taxa de erro: valor absoluto da diferença dos valores da reta(pertencente ao gráfico de correlação do X e Y) e os valores dentro da base
  	- Obs: Só fazer isso  se a minha variável tiver correlação alta
 
Logaritmo niperiano(?)
