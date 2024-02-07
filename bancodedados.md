# Banco de Dados

## Semana 1: Introdução a banco de dados e modelo entidade relacionamento


### Banco de Dados:

- Um banco de dados é uma coleção de dados.
- Um dado é um fato que deve ser armazenado.
- Diz respeito a algum aspecto do mundo real e é criado com foco em um propósito específico (um objetivo).
- Tem uma estrutura lógica que confere um significado aos dados.

### Independência entre dados e programa:

- Que não fazem uso de um SGBD e de um  banco de dados: Incorporam as estruturas de dados e fazem o controle de acesso a esses dados.

- Que fazem uso de um SGBD e de um bancod de dados:Não precisam lidar com o armazenamento e o controle de acesso aos dados.

### Independência entre operações e programas:

- Os SGBDs permitem que operações sobre os dados sejam definidas de maneira independente da aplicação.

- As aplicações podem chamar tais operações por meio de seus nomes e argumentos, e não se preocupam como tais operações são implementadas.

### Abstração de Dados:

- O modelo de dados conceitual é construiído por um analista de dados, e sua implementação física é realizada em um SGBD.

### Usuários:

- **Administradores:** (DBA - Database Administrator)
- **Projetistas:** (Database Designers)
- **Analistas:** (Analistas de sistemas e programadores de aplicação)
- **Usuários finais.**

### Vantagens da Abordagem baseada em SGBDS:

- Se diferentes instâncias de um mesmo dado são armazenadas em locais diferentes e gerenciadas por aplicações diferentes, corre-se o risco de criar inconsistência de dados.

- **Controle de redundância:** Todos os dados estão armazenados em um único lugar, e diferentes aplicações acessam a mesma instância desses dados.

- **Controle de acesso:** O SBGD oferece um subsistema de autorização e segurança que previne que usuários acessem dados sem que estejam autorizados.

- **Persistência para programas e estruturas de dados (objetos):** Códigos e estruturas de dados são armazanados e gerenciados pelos SGBDs como objetos - são nomeados e podem ser invocados, alterados e excluídos a partir de funcionalidades oferecidas pelo sistema.

- **Eficiência no processamento de consultas:** Os SGBDs possuem funcionalidades que permitem executar requisições sobre os dados de forma eficiente. Essas funcionalidades incluem gerenciamento de índices e de memória, e otimização de consultas.

- **Oferecimento de sistemas de backup e recuperação:** SGBDs oferecem subsistemas que realizam a recuperação dos dados após a ocorrência de falhas de software e hardware.

- **Garantia das restrições de integridade:** Os dados armazenados em um banco de dados são associados a algumas restrições. Tais restrrições são constantemente verificadas, e garantidas pelo SGBD.

- **Garante padrões**
- **Reduz o tempo de desenvolvimento de aplicações**
- **Fornece flexibilidade e disponibilidade**
- **Promove economia de escala**

### Modelos de Dados:

- **Modelos de alto nível ou modelos de dados conceituais:** fornecem conceitos que são próximos a forma como os usuários percebem os dados. Ex: Modelo Entidade - Relacionamento.

- **Modelos de baixo nível ou modelos de dados físicos:** Fornecem conceitos que descrevem em detalhes como os dados são armazenados no meio de persistência. Ex: Formato de registros, ordenação e formas de acesso.

- **Modelos de dados de representação (ou implementação):** Fornecem conceitos que são compreensíveis por parte dos usuários mas que não estão longe da maneira como os dados são aramazenados no meio de persistência. Ex: Modelo Relacional.

### Esquemas, Instâncias e Estado do Banco de Dados:

- **Esquema:** Descrição de um banco de dados. É especificado durante o projeto do banco de dados e não é esperado que sofra mudanças frequentes.

- **Instância (Estado):** Os dados armazenados em um banco de dados em um momento particular (tempo). Muitos (diferentes) estados de um banco de dados podem ser construídos a partir de um mesmo esquema.

### Linguagens:

- **Linguagem de definição de dados (DDL):** É usada para definir o esquema do banco de dados.
    - Atualmente pode englobar a SDL - Linguagem de definição de armazenamento - e a VDL - Linguagem de definição de visão.

- **Liguagem de manipulação de dados (DML):** É usada para executar instruções de recuperação, inserção, exclusão e modificação de dados.

### Elementos do Diagrama ER:

- **Entidades**
- **Atributos**
- **Chaves**
- **Relacionamentos**
- **Cardinalidades**

### Modelo ER:

- **Relacionamentos:** Representam as associações existentes entre as entidades.

- **Heurística:** No discurso que descreve o mundo real, os relacionamentos são geralmente expressos por ações que envolvem entidades.

### Diagrama ER - Relacionamentos:

No diagrama ER, os relacionamentos são representados por losangos.

### MER Conceitos:

- Um tipo relacionamento R entre n entidades, E1, E2, ..., En, define um conjunto de associações - ou um conjunto relacionamento - entre entidades desses tipos entidade.

### Relacionamento - Grau:

- O grau de um tipo relacionamento é o número de tipos entidade participantes do relacionamento:
    - binário (ou de grau dois)
    - ternário (ou de grau tres)
    - n-ário (ou de grau n)

Exemplo: Um fornecedor fornece peças para um projeto. O relacionamento FORNECE envolve as entidades FORNECEDOR, PEÇA e PROJETO.

### Relacionamento Recursivo:

- Ocorre quando um mesmo tipo de entidade participa mais de uma vez do tipo relacionamento, assumindo papéis diferentes.

- Tipo entidade: FUNCIONARIO
- Tipo relacionamento: SUPERVISIONA

### Cardinalidade:

- Especifica o número máximo de instâncias de relacionamento nas quais uma instância de entidade pode participar.

    - 1:1 (um para um)
    - 1:N (um para muitos)
    - N:1 (muitos para um)
    - M:N (muitos para muitos)

A cardinalidade está associada a um relacionamento e no diagrama ER é representada por 1, M e N (...) junto aos losangos.

- 1:1 FUNCIONÁRIO, 1, **GERÊNCIA**, 1, DEPARTAMENTO
- 1:N DEPARTAMENTO 1, **CONTROLA**, N, PROJETO
- N:1 FUNCIONÁRIO N, **TRABALHA_PARA**, 1, DEPARTAMENTO
- M:N FUNCIONÁRIO M, **TRABALHA_EM**, N, PROJETO
- 1:N (RECURSIVO) - FUNCIONÁRIO 1, **SUPERVISIONA**, N, FUNCIONÁRIO

### Restrição de Participação:

- Especifica se uma entidade individual precisa, necessariamente, estar associada a outra entidade individual via um tipo relacionamento. Se a participação em um tipo relacionamento é obrigatória, ela é dita TOTAL, senão ela é dita PARCIAL.

- No diagrama ER a participação total é representada por uma linha dupla que conecta o tipo entidade ao tipo relacionamento. A participação parcial é representada pela linha simples.


## Semana 2: Modelo relacional e mapeamento do modelo entidade-relacionamento para o modelo relacional

## Semana 3: Sistemas de gerenciamento de banco de dados de mercado e normalização

## Semana 4: Introdução a linguagem SQL, Indexação e ferramentas de manipulação de banco de dados

## Semana 5: Consultas usando SQL

## Semana 6: Consultas combinadas de tabelas usando SQL e conceitos de View e Data Lake

## Semana 7: Transações e Introdução a banco de dados não relacionais

## Semana 8: Bancos de dados NoSQL - MongoDB. Revisão


## Quiz

