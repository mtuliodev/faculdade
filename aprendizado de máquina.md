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
  - Algoritmo zeroR(régua):
    - Não cria nenhuma regra
    - Atribui todos os registros a uma classe majoritária
    - Serve como baseline para avaliar a qualidade dos modelos, ou seja, se ele acerta 80%, todos os meus algoritmos mais complexos devem acertar de 80% pra cima
  - Algoritmo OneR
    - Usado para encontrar o atributo mais relevante, a raíz da arvore
    - Seleciono uma coluna de atributo como antecedente, e outra como conseguinte que é a classe. A partir disso, eu faço um filtro por todos os valores distintos da coluna de atributo e todos os valores diferentes que ele atingiu na classe
    - A coluna que tiver menos erros pela classe, é a raíz(atributo mais relevante)
  - Algoritmo PRISM
    - A partir da classe, eu filtro por cada valor distinto dela e tento identificar algum padrão que existe nas outras colunas dentro desse valor distinto
      - Ex: Se na minha classe de risco, no valor alto, todos os valores são mais de 1000, então se o valor é mais de 1000, o meu risco é alto 
  
    
