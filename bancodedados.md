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

- Administradores:(DBA - Database Administrator)
- Projetistas:(Database Designers)
- Analistas:(Analistas de sistemas e programadores de aplicação)
- Usuários finais.

### Vantagens da Abordagem baseada em SGBDS:

- Se diferentes instâncias de um mesmo dado são armazenadas em locais diferentes e gerenciadas por aplicações diferentes, corre-se o risco de criar inconsistência de dados.

- Controle de redundância: todos os dados estão armazenados em um único lugar, e diferentes aplicações acessam a mesma instância desses dados.

- Controle de acesso: o SBGD oferece um subsistema de autorização e segurança que previne que usuários acessem dados sem que estejam autorizados.

- Persistência para programas e estruturas de dados (objetos): códigos e estruturas de dados são armazanados e gerenciados pelos SGBDs como objetos - são nomeados e podem ser invocados, alterados e excluídos a partir de funcionalidades oferecidas pelo sistema.


## Semana 2: Modelo relacional e mapeamento do modelo entidade-relacionamento para o modelo relacional

## Semana 3: Sistemas de gerenciamento de banco de dados de mercado e normalização

## Semana 4: Introdução a linguagem SQL, Indexação e ferramentas de manipulação de banco de dados

## Semana 5: Consultas usando SQL

## Semana 6: Consultas combinadas de tabelas usando SQL e conceitos de View e Data Lake

## Semana 7: Transações e Introdução a banco de dados não relacionais

## Semana 8: Bancos de dados NoSQL - MongoDB. Revisão