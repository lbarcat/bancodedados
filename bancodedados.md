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

### Modelo Relacional:

- Modelo de dados que representa um banco de dados como uma coleção de relações. Uma relação remete a uma tabela de valores, na qual cada linha representa uma coleção de valores (colunas) relacionados.

Uma linha representa um fato que tipicamente corresponde a uma entidade ou relacionamento do mundo real.

- Glossário para o modelo relacional:
    - Relação -> tabela
    - Tupla -> linha (registro)
    - Atributo -> coluna (campo)
    - Domínio -> tipo de dado

### Ordenação de Registros em uma tabela:

Uma tabela é definida como um conjunto de registros. Elementos de um conjunto não são ordenados. Assim, os registros em uma tabela não possuem nenhuma ordenação.

## Ordenação de Valores dentro de um registro:

Um registro é uma lista ordenada de valores, então a ordem do valores no registro é importante.
    - Para efeitos práticos, e em determinadas situações, essa restrição pode ser flexibilizada.

## Valores e NULL nos registros:

Cada valor em um registro é um valor atômico. Assim, atributos compostos e atributos multivalorados não são permitidos.

Valores **NULL** são usados para representar os valores desconhecidos ou que não se aplicam aquele atributo naquele registro.

## Restrições de Domínio:

Restrições de domínio especificam que o valor de cada atributo A deve ser um valor atômico dentro de um domínio dom(A), em todos os registros da tabela.

## Restrições de Chave:

Por definição, todos os elementos de um conjunto são distintos, logo, todos os registros em uma tabela devem ser distintos, ou seja, dois registros quaisquel não podem ter a mesma combinação de valores para todos os seus atributos.

- r1[SK] <> r2[SK]

## Superchave:

Qualquer conjunto de atributos SK. Toda relação tem pelo menos uma superchave - todos os seus atributos. Uma superchave pode ter atributos redundantes.

## Chave:

É uma superchave de T sem atributos redundantes; i.e. é um conjuntode atributos mínimo capaz de garantir a restrição de unicidade.

## Conceitos de Chave:

- Em geral, uma tabela T pode ter mais de uma chave. Cada uma delas é uma **chave candidata**.

- É comum escolher uma das chaves candidatas para ser a **chave primária** da relação.

- Cada uma das demais chaves candidatas é chamada de **chave única**.

## Restrição de Integridade:

- **Restrição de integridade de entidade:** o valor de uma chave primária não pode ser NULL.

- **Restrição de integridade referencial:** é especificada entre duas tabelas e usada para manter a consistência entre os seus registros.
    - Um registro de uma tabela A que referencia uma tabela B deve fazer a referência a um **registro existente** na tabela B.

## Chave Estrangeira:

Considere dois esquemas de tabela T1 e T2. Um conjunto de atributos FK no esquema T1 é uma chave estrangeira de T1 que referencia T2 se:

    - os atributos em FK tem o mesmo domínio dos atributos da chave primária PK em T2;

    - o valor de FK no registro r1 de um estado de t1(T1) ou ocorre como um valor de PK para algum registro r2 de um estado de t2(T2) ou é NULL.

## Mapeamento MER -> Relacional:

**Mapeamento:** uma forma de projetar um esquema de um banco de dados relacional (um projeto lógico) tendo como base o esquema de um projeto conceitual.

A maneira clássica de desenvolvimento de um banco de dados é por meio da construção de um modelo conceitual - **independente de SGBD** - o qual é posteriormente convertido, ou mapeado, para um projeto lógico que seja **implementável no SGBD** escolhido para desenvolvimento do sistema de banco de dados.

Ao implementarmos o projeto lógico no SGBD teremos **garantidas** algumas **restrições** que devem ser impostas aos dados.

Exemplo:
    - Restrições de **domínio**
    - Restrições de **chave**
    - Restrições de **integridade referencial**
    (chave estrangeira)

Mapeando tipos entidade fortes (ou regulares):

- Para cada tipo entidade forte em um MER é criada uma tabela no modelo Relacional;

- Essa tabela inclui todos os atributos simples, e os componentes simples dos atributos compostos, do tipo entidade forte;

- Um atributo chave da entidade é escolhido como chave primária para a tabela recém-criada.

Exemplo:

- FUNCIONÁRIO
    - IDENT.
    - DT NASC
    - NOME
        - P_NOME
        - SOBRENOME
    - ENDEREÇO
    - SALÁRIO
    - SEXO

**Mapeando os atributos multivalorados:** para cara um desses atributos é preciso criar uma nova tabela.

- essa tablea incluirá um atributo A correspondente ao atributo multivalorado, mais o atributo chave primária K da tabela que representa o tipo entidade no qual o atributo multivalorado foi especificado; 

- o atributo K será uma chave estrangeira na nova tabela;

- a chave primária dessa nova tabela será a combinaçã dos atibutos A e K.

**Mapeando tipos entidade fracas:**

- para cada tipo entidade fraca em um MER é criada uma tabela no modelo Relacional;

- essa tabela inclui todos os atributos simples, e os componentes simples dos atributos compostos, do tipo entidade fraca; e inclui como atributo chave estrangeira, a chave da entidade forte associada a entidade fraca;

- a chave primária da tabela criada é a combinação do atributo chave da entidade forte com o atibuto chave parcial da entidade fraca.

## Mapeando tipos de Relacionamentos Binários 1:1:

- Para cada tipo relacionamento binário 1:1 no MER, identifique as tabelas S e T que correspondem aos tipos entidade participantes no relacionamento.

FUNCIONÁRIO -> 1 -> GERÊNCIA -> 1 -> DEPARTAMENTO

Escolhas uma **abordagem:**

1 - Abordagem da chave estrangeira (mais comum)




## Semana 3: Sistemas de gerenciamento de banco de dados de mercado e normalização

## Semana 4: Introdução a linguagem SQL, Indexação e ferramentas de manipulação de banco de dados

## Semana 5: Consultas usando SQL

## Semana 6: Consultas combinadas de tabelas usando SQL e conceitos de View e Data Lake

## Semana 7: Transações e Introdução a banco de dados não relacionais

## Semana 8: Bancos de dados NoSQL - MongoDB. Revisão


## Quiz

