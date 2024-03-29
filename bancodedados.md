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

### Ordenação de Valores dentro de um registro:

Um registro é uma lista ordenada de valores, então a ordem do valores no registro é importante.
    - Para efeitos práticos, e em determinadas situações, essa restrição pode ser flexibilizada.

### Valores e NULL nos registros:

Cada valor em um registro é um valor atômico. Assim, atributos compostos e atributos multivalorados não são permitidos.

Valores **NULL** são usados para representar os valores desconhecidos ou que não se aplicam aquele atributo naquele registro.

### Restrições de Domínio:

Restrições de domínio especificam que o valor de cada atributo A deve ser um valor atômico dentro de um domínio dom(A), em todos os registros da tabela.

### Restrições de Chave:

Por definição, todos os elementos de um conjunto são distintos, logo, todos os registros em uma tabela devem ser distintos, ou seja, dois registros quaisquel não podem ter a mesma combinação de valores para todos os seus atributos.

- r1[SK] <> r2[SK]

### Superchave:

Qualquer conjunto de atributos SK. Toda relação tem pelo menos uma superchave - todos os seus atributos. Uma superchave pode ter atributos redundantes.

### Chave:

É uma superchave de T sem atributos redundantes; i.e. é um conjuntode atributos mínimo capaz de garantir a restrição de unicidade.

### Conceitos de Chave:

- Em geral, uma tabela T pode ter mais de uma chave. Cada uma delas é uma **chave candidata**.

- É comum escolher uma das chaves candidatas para ser a **chave primária** da relação.

- Cada uma das demais chaves candidatas é chamada de **chave única**.

### Restrição de Integridade:

- **Restrição de integridade de entidade:** o valor de uma chave primária não pode ser NULL.

- **Restrição de integridade referencial:** é especificada entre duas tabelas e usada para manter a consistência entre os seus registros.
    - Um registro de uma tabela A que referencia uma tabela B deve fazer a referência a um **registro existente** na tabela B.

### Chave Estrangeira:

Considere dois esquemas de tabela T1 e T2. Um conjunto de atributos FK no esquema T1 é uma chave estrangeira de T1 que referencia T2 se:

- os atributos em FK tem o mesmo domínio dos atributos da chave primária PK em T2;

- o valor de FK no registro r1 de um estado de t1(T1) ou ocorre como um valor de PK para algum registro r2 de um estado de t2(T2) ou é NULL.

### Mapeamento MER -> Relacional:

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

### Mapeando tipos de Relacionamentos Binários 1:1:

- Para cada tipo relacionamento binário 1:1 no MER, identifique as tabelas S e T que correspondem aos tipos entidade participantes no relacionamento.

FUNCIONÁRIO -> 1 -> GERÊNCIA -> 1 -> DEPARTAMENTO

Escolhas uma **abordagem:**

1 - Abordagem da chave estrangeira (mais comum)
2 - Abordagem da relação unificada
3 - Abordagem referência cruzada ou relação de relacionamento

- **Abordagem da chave estrangeira:**
    - escolha uma das tabelas, por exemplo a tabela S - e inclua como chave estrangeira em S a chave primária de T;
    - se houver tipo entidade com participação total envolvido no relacionamento, escolhê-lo para o papel de S será a melhor opção;
    - inclua todos os atributos simples, e os componentes simples dos atributos compostos, do tipo relacionamento como atributos de S.

- **Abordagem da relação unificada:**
    - unifique os dois tipos entidade e o tipo relacionamento é uma única tabela.
    - isso é possível quando ambos os tipos entidade possuem participação total, indicando que as duas relações referentes aos tipos entidade participantes do relacionamento possuem sempre o mesmo número de registros.

- **Abordagem referência cruzada:**
    - crie uma terceira tabela para atuar como uma referência cruzada das chaves primárias de cada uma das duas tabelas S e T;
    - a terceira tabela incluirá as chaves primárias de S e T como chaves estrangeiras;
    - a chave primária da terceira tabela será uma das duas chaves estrangeiras, e a outra chave estrangeira será uma chave única.

### Mapeando tipos de relacionamentos binários 1:N (N:1):

- para cada tipo relacionamento regular binário 1:N, identifique a tabela S que representa o tipo entidade que participa do tipo relacionamento uma vez.

- inclua a chave primária da tabela T (a outra entidade que participa do relacionamento) como chave estrangeira na tabela S;

- inclua como atributo de S todos os atirbutos simples, e os componentes simples dos atributos compostos, do tipo relacionamento.

### Mapeando tipos de relacionamentos binários M:N:

- para cada tipo relacionamento binário M:N crie uma nova tabela para representar o relacionamento;

- inclua como chaves estrangeiras na nova tabela as chaves primárias das tabelas que representam as entidades participantes do relacionamento;

- a chave primária da nova tabela é a combinação dessas chaves estrangeiras;

- também inclua todos os atributos simples, ou componentes simples de atributos compostos, como atributos na nova tabela.

## Semana 3: Sistemas de gerenciamento de banco de dados de mercado e normalização

### Market Share - Banco de dados (infinidade de rankings):

- Oracle
- MySQL
- Microsoft SQL Server
- PostgreSQL
- MongoDB
- IBM Db2
- Redis
- Elasticsearch
- SQLite
- Microsoft Access

### Elementos que compõem o Score:

- Número de menções em Websites (Google e Bing)
- Interesse no sistema (Google Trends)
- Frequência de discussão em listas relevantes:
    - Stack Overflow e DBA Stack Exchange
- Número de ofertas de emprego:
    - Indeed e Simply Hired
- Número de Perfis profissionais que os sistemas são mencionados (LinkedIn)
- Número de menções em rede social (Twitter)

### Tipos de bancos:

- 7 dos 10 sistemas listados são primariamente BD **relacionais.:**
    - Oracle, MySQL, SQL Server, PostgreSQL, DB2, SQLite e Access
- MongoDB é de **documentos**
- Redis é **chave-valor**
- Elasticsearch é **mecanismo de busca**
- 8 deles sai de modelos múltiplos:
    - Relacional, Documentos, Grafos, Espacial, RDF, time séries
 
### Breve abordagem sobre os mais utilizados:

- A probabilidade de atuar com banco de dados usando Oracle, MySQL, PostgreSQL ou SQL Server é extremamente grande.

- Importante observar os detalhes desses produtos.

- Atualmente, com o advento do Big Data e das possibilidades tecnológicas disponíveis, bancos do tipo chave-valor, de documentos e de grafos passam a ser muito recorrentes também, mas ainda com uso restrito.

### Oracle:

- Uma das ferramentas mais usadas e robustas do mercado.
- Tem como principal virtude a robustez e confiabilidade.
- Empresa: Oracle
- Desde: 1980
- Site: www.oracle.com/database
- Licença comercial (com uma versão express)
- Multiplataforma (AIX, HP-UX, Linux, OS X, Soalris, Windows, z/OS)
- Suporta SQL

### MySQL:

- MySQL AB foi comprada pela Sun, que foi comprada pela Oracle em 2009.
- Integração com PHP foi uma grande sacada, pequenos projetos migraram rapidamente para MySQL.
- Empresa: Oracle
- Desde: 1995
- Site: www.mysql.com
- Open Source
- Multiplataforma (FreeBSD, Linux, OS X, Solaris, Windows)
- Suporta SQL

### SQL Server:

- Um dos primeiros banco de dados do mercado. Por muito tempo ficou restrito a plataforma Windows. Sempre prezou por uma interface amigável.
- Empresa: Microsoft
- Desde: 1989
- Site : wwww.microsoft.com/en-us/sql-server
- Licença comercial (com uma versão express)
- Multiplataforma (Windows e Linux)
- Suporta SQL

### PostgreSQL

- Muito robusto, muito utilizado em sistemas com muitos registros, um dos primeiros open source a implementar UTF-8. Com certeza, uma ferramenta open source (além de BD) das mais exepcionais.
- Responsável: PostgreSQL Global Development Group
- Desde: 1989
- Site: wwww.postgresql.org
- Open Source
- Multiplataforma (FreeBSD, HP-UX, Linux, NetBSD, OpenBSD, OS X, Solaris, Unix, Windows)
- Suporta SQL

### Como escolher?

- Compreender a variedade de critérios que podem ter impacto.
- Opção sempre por um software open source (ou, mais simplesmente, por um não pago)?
- Plataforma
- Implementação em Cloud - Oferecido como DBaaS;
- Restrição com conectores ou linguagens;
- Escolha por modelo (relacional, objetos, grafo...);
- Tecnologias como controle de transações, triggers, stored procedures, map reduce, entre outros. 

### O que muda baseado na escolha?

- Como bancos de dados são todos parecidos.
- Um SQL padrão funciona em todos.
- Há especificações da linguagem SQL, que são para uso exclusivo com determinados produtos (como funções). Isso pode determinar retrabalho em uma futura mudança de opção de produto.
- O mesmo serve para outros recursos do SGBD.
- Há ferramentas específicas (nativas ou não) para cada produto.

### Normalização:

- Dependências Funcionais:
    - Uma dependência funcional (DF) é uma restrição imposta a dois conjuntos de atributos de um banco de dados.

    - Trata-se de uma restrição que é estabelecida pelo projetista do banco de dados, de acordo com as regras que valem no mundo real que está sendo modelado.

    - É uma ferramenta que permite estabelecer uma formalização para a avaliação da qualidade do projeto de bando de dados.

### Dependências Funcionais:

- Uma dependência funcional é uma propriedade semântica dos atributos, e por isso ela é derivada do conhecimento que o projetista do banco de dados tem do mundo real que está sendo modelado.

- O principal uso das dependências funcionais é descrever um esquema de tabela de forma mais detalhada, por meio da especificação de restrições em seus atributos que devem ser garantidas todo o tempo.

- Não pode haver instâncias de relações no banco de dados que violem as dependências funcionais estabelecidas pelo projetista do banco de dados.
- Devemos garantir que as dependências funcionais não estão sendo violadas:
    - Primeiro (preferível): estabelecendo um bom projeto de banco de dados.
    - Segundo: implementando funções.

### Formas normais:

- A qualidade de um projeto de banco de dados pode ser medida a partir da verificação da forma normal que ele alcança.
    - primeira forma normal
    - segunda forma normal
    - terceira forma normal
    - Boyce-Codd Normal Form - BCNF

- Normalização:
     - O processo de normalização é dirigido pela informação referente as dependências funcionais e as chaves dos esquemas de tabelas
     - É um processo de análise e adequação dos esquemas de tabelas com o objetivo de minimizar redundâncias e anomalias de inserção, exclusão e alteração.

No processo de normalização, esquemas de tabela que não satisfazem certas condições, são decompostos em esquemas de tabela menores que satisfazem as tais condições e ainda possuem algumas propriedades desejáveis.

- A forma normal de uma tabela é a mais alta foram normal cujas condições são atendidas pela tabela.

- A forma normal de um projeto de banco de dados é aquela referente a sua tabela em mais baixa forma normal.

- Considerar apenas as formas normais não garante que o projeto de banco de dados está bom. É ainda preciso considerar algumas propriedades adicionais.


## Semana 4: Introdução a linguagem SQL, Indexação e ferramentas de manipulação de banco de dados

### Ferramentas Case MySQLWorkbench

### Ferramentas Case:

- Uma ferramenta CASE é um produto baseado em computador que tem o propósito de ajudar os engenheiros de software em atividades relacionadas ao processo de desenvolvimento de software (baseado na definição de ferramenta CASE do Carnegie Mellon Software Engineering Institute).

- Ferramentas CASE para modelagem de Banco de Dados:
    - Ajudar na criação de **Modelos Entidade Relacionamento**
    - Ajudar na criação de **Modelos Relacionais**
    - Disponibilizar funcionalidades de criação automática de **Dicionário de Dados**
    - Disponibilizar funcionalidades de criação de **scripts** de geração de banco de dados para tecnologias de SGBDs.
    - Possibilitar a **Engenharia Reversa**

É esperado que uma ferramenta CASE disponibilize **funcionalidades de verificação** quanto às regras que definem um modelo, ou que definem qualquer outro artefato do processo de desenvolvimento de software suportado por ela.

- Exemplos de ferramentas CASE com recursos para atividades de modelagem de banco de dados.

- Variações de valores, implementações, modelos lógicos, acesso a especificações comerciais.

    - DBDesigner
    - ERWIN
    - DB-MAIN
    - IBM Rational
    - MySQLWorkbench

### MySQLWorkbench:

- Sem custo, MySQL, multiplataforma
- Acessso: https://www.mysql.com/products/workbench/
- Ferramenta visual unificada para arquitetos de banco de dados, desenvolvedores e DBAs.
- Fornece modelagem de dados, engenharia reversa, desenvolvimento de SQL e ferramentas de administração abrangentes para configuração de servidor, administração, de usuário, backup e muito mais.

### Engenharia Reversa:

Em algumas situações há a disponibilidade do banco de dados implementado, mas não se conhece o modelo conceitual/relacional do mesmo.

A Engenharia Reversa é a capacidade da Ferramenta CASE de acessar um banco de dados implementado e a partir dele gerar um modelo conceitual (geralmente baseado em MER).

### Engenharia Reversa - MySQLWorkbench:

É iniciada a partir do menu Database na opção Reverse Engineer, e na sequência será solicitada a conexão ao banco onde irá ocorrer a engenharia reversa.

### Novo Modelo - MySQLWorkbench:

- Criar uma implementação de banco de dados relacional, a partir de um modelo ER.
- Lembre-se sempre de salvar o modelo e da possibilidade de gerar um script SQL a partir do modelo.

- O MySQLWorkbench não é exatamente uma ferramenta
case, porque ele não faz implementações de nível apenas
conceitual.
- O MySQLWorkbench pode ser considerado uma ferramenta
de desenvolvimento para MySQL.
- Entretanto, ela permite pensar de forma conceitual e a partir
disso gerar uma implementação física.
- É muito difícil e improdutivo trabalhar com banco de dados
sem uma ferramenta de desenvolvimento como essa. 

## Semana 5: Consultas usando SQL

## Semana 6: Consultas combinadas de tabelas usando SQL e conceitos de View e Data Lake

## Semana 7: Transações e Introdução a banco de dados não relacionais

## Semana 8: Bancos de dados NoSQL - MongoDB. Revisão


## Quiz