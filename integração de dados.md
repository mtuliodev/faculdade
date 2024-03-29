# Aulas anteriores

- Análise Descritiva (ver o que aconteceu no passado)
- Análise Preditiva
    - Identificar tendências e fazer estratégias para o futuro
- Análise Prescritiva
    - Sugerir ações para avaliar cenários e identificar possíveis saídas em uma determinada situação (‘O que vamos fazer?)

- **Dado --> Informação 🡪 Conhecimento**

### Diferença entre Integração, Replicação e Migração de dados
- **Integração de dados:** Mover diferentes dados de uma determinada fonte para um repositório de dados centralizado
- **Replicação de dados:** Fazer cópias dos dados em locais diferentes, para melhorar a disponibilidade/resiliência do sistema
- **Migração de dados:** Movimentação de dados para uma plataforma diferente


- BPM → Business Process Management
- BPMN → Business Process Model and Notation
- OLTP → Online Transaction Processing
- OLAP → Online Analytics Processing
- PDCA → Plan/Do/Control/Act
- GUI → Graphic User Interface
- Curva de aprendizado → O tempo para o usuário aprender a usar o programa/site

### Tipos de repositório de dados
- Data Warehouse: base/banco com todos os dados
- Data Mart: base/banco com todos os dados, mas não consegue armazenar uma quantidade grande de dados
- Data Lake: Quando eu uso o Data Mart e o Warehouse juntos


# Aula 20/02
## ETL
- Extract, Transform and Load
### Ferramentas de ETL
- Transportam dados
- Documentam a alteração dos metadados ao longo do tempo
- Realizam a gestão de erro, os logs e estatísticas
- Maneiras para escolher uma ferramenta de ETL:
  - Capacidade de ler e transcrever as fontes de dados
  - Captura e entrega automática de metadados
  - Histórico de alterações
  - Boa interface de UX   
### Objetivo
- Abastecer o Data Warehouse com dados limpos

# Aula 27/02
## Metodologia dos projetos de BI&A
- Planejamento
    - Concepção do projeto
    - Definição dos objetivos
    - Definição da equipe
    - Identificação de riscos e restrições
    - Detalhamento de requisitos e definição do escopo
    - Definição de infraestrutura
    - Elaboração de plano do projeto
- Levantamento
    - Entendimento do negócio
    - Levantar relatórios existentes
    - Definição de indicadores
    - Especificações técnicas
- Modelagem
    - Arquitetura do DW
    - Definir os fatos, métricas e dimensões
    - Definir a granularidade de informações(?)
    - Projeto do banco de dados
- Extração e carga(ETL)
    - Definir estratégias
    - Implementar rotinas
    - Promover integração de dados
    - Validar dados carregados
- Aplicações BI&A
- Transição
    - Validação do ambiente
    - Treinamento dos usuários
    - Suporte
    - Implantação
  
# Aula 29/02
## DW
- Data warehousing: Desenho, construção, uso e manutenção do data warehouse

## Etapas de construção de DW
- Levantamento de requisitos
- Modelagem multidimensional
- ETL
- Visualização de resultados

## Perguntas a serem feitas ao cliente
- O que estamos avaliando?
- Como serão avaliados/analisados?
- Qual o nível mais baixo de detalhe de informações?(ou seja, uma informação específica)
- Como se espera agrupar/sumarizar as informações?

# Aula 05/03
## BD Operacional x DW

| -------- | BD Operacional | Data Warehouse |
| Usuários | Funcionários | Alta administração | 
| Utilização | Tarefas cotidianas | Estratégia |
| Princípio de funcionamento | Por transações | Por análise de dados |
| Detalhamento | Alto | Sumarizado |
| Padrão de uso | Previsível | Difícil de prever |
| Organização dos dados | Orientado a aplicações | Orientado a assunto |

