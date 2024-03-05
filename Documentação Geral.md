# Rate It

## Plataforma de avaliação de filmes

**Gabriel dos Santos de Castro**

## Resumo

Rate It é uma plataforma de avaliação de filmes idealizada com o intuito de facilitar a avaliação de filmes catalogados com a finalidade de que o usuário final possa filtrar o que lhe agrada ou não. Os conceitos mais gerais da aplicação envolvem as entidades dos filmes, avaliações, usuários, que também incluem o administrador do sistema e, finalmente, os membros da equipe de cada filme.

## Sumário

- [[Documentação Geral#1 Introdução| 1 Introdução]]
    - [[Documentação Geral#1.1 Objetivo Geral| 1.1 Objetivo Geral]]
    - [[Documentação Geral#1.2 Objetivos Específicos| 1.2 Objetivos Específicos]]
    - [[Documentação Geral#1.3 Materiais e métodos| 1.3 Materiais e Métodos]]
- [[Documentação Geral#2 Apresentação do Projeto| 2 Apresentação do Projeto]]
    - [[Documentação Geral#2.1 Escopo do Projeto| 2.1 Escopo do Projeto]]
    - [[Documentação Geral#2.2 Levantamento de requisitos| 2.2 Levantamento de Requisitos]]
        - [[Documentação Geral#2.2.1 Requisitos Funcionais| 2.2.1 Requisitos Funcionais]]
        - [[Documentação Geral#2.2.2 Regras de Negócio| 2.2.2 Regras de Negócio]]
        - [[Documentação Geral#2.2.3 Requisitos Não Funcionais Tecnológicos| 2.2.3 Requisitos Não Funcionais Tecnológicos]]
- [[Documentação Geral#3 Diagramas de análise e modelagem do sistema| 3 Diagramas de análise e modelagem do sistema]]
    - [[Documentação Geral#3.1 Diagrama de Entidade Relacionamento| 3.1 Diagrama de Entidade Relacionamento]]


## 1 Introdução

Hoje em dia o acesso a filmes foi muito facilitado, seja através de cinemas ou até mesmo plataformas online como a Netflix, mas o problema surge quando o usuário final não sabe o que assistir, visto que se sente como um cliente diante de um cardápio infindável dos mais diversos tipos de filme. Assim, é proveitosa a utilização de uma plataforma de avaliação de filmes na qual o usuário possa ler e fazer avaliações para que possa haver uma métrica de quais filmes tem agradado ou não ao público. O Rate It foi idealizado exatamente para suprir essa demanda. 

## 1.1 Objetivo Geral

Desenvolver uma plataforma simples de avaliação de filmes na qual o usuário possa acessar um catalogo específico de filmes, que deve ser cadastrado pelo administrador do sistema, e por fim fazer avaliações atribuindo notas e comentários aos filmes.

## 1.2 Objetivos Específicos

Os objetivos específicos deste projeto incluem:

- Criar uma ambiente virtual de avaliação de filmes
- Avaliar filmes e incentivar o bom gosto pela arte 
- Incentivar a industria cinematográfica

## 1.3 Materiais e métodos

Este projeto foi idealizado para ser implementado de forma independente por mim mesmo, porém caso haja a necessidade de manutenções futuras ou adição de novas funções ao sistema, poderão ser adicionados novos desenvolvedores assim surgindo a necessidade da utilização de algum método de desenvolvimento em grupo, como por exemplo o Team Development. Tendo claro esse ponto, podemos agora prosseguir para as demais tecnologias e métodos utilizados.

O projeto foi dividido em Front-end e Back-end, a fim de facilitar a segregação de atribuições e responsabilidades de cada parte do código. Para atingir esse objetivo foram utilizadas diversas tecnologias e métodos citadas abaixo.

**Observação**: Note que a documentação está inteiramente escrita em português brasileiro, porém o código, banco de dados e todos os elementos respectivos à programação e implementação do sistema estão em inglês, isso inclui nomes de variáveis, funções, tabelas SQL, e dentre outros. Isso ocorre para evitar o uso de acentos e caracteres indesejados no código, além de manter os algoritmos mais legíveis, dando acesso à milhares de falantes de inglês ao redor do mundo.

O Back-end engloba uma série de partes que compõem a seção "invisível" para o usuário final que são: o banco de dados, idealizado com um diagrama de Entidade e Relacionamento (ER) feito no **pgAdmin4** e implementado com **PostgreSQL**. A API, que faz a ponte entre o Front-end e o banco de dados através de requisições HTTP, foi implementada utilizando JavaScript em sua versão **ECMAScript 2021 (ES2021)**. Além disso a API é executada pelo ambiente de execução chamado de **Node JS** que está em sua versão 20.11.0, juntamente do **npm** (Gerenciador de pacotes do node) que está em sua versão 10.2.4. Para atingir os objetivos da aplicação foram utilizadas diversas bibliotecas (pacotes), como por exemplo o **Express**, que facilita a criação de um servidor Node JS, além da criação e manutenção de rotas dentro da API.

O Front-end, parte que compreende a interface do usuário (UI), foi feita utilizando o framework React JS, cujo código é escrito em JavaScript, JSX e Sass para a estilização dos componentes.

Além disso, o **Git** e **GitHub** foram utilizados para versionar e armazenar os códigos ao longo do desenvolvimento da aplicação. 

Para modelar o projeto, foi utilizado a linguagem **UML 2.0 (Unified Modeling Language, ou em português Linguagem de Modelagem Unificada)**. A UML é uma linguagem padronizada que permite a modelagem visual de sistemas, utilizando diagramas que representam diferentes aspectos da aplicação, como estrutura, comportamento e interações entre os componentes.

A documentação foi escrita em Markdown através do software Obsidian e também foi versionada e armazenada com Git e GitHub.

Eis as tecnologias apresentadas em formato de lista:
- pgAdmin4
- PostgreSQL
- JavaScript
- Node JS
- npm
- Express
- React JS
- JSX
- Sass
- Git
- GitHub
- UML 2.0
- Markdown
- Obsidian

## 2 Apresentação do Projeto

### 2.1 Escopo do Projeto

Esse projeto da acesso a todo um acervo de avaliações de filmes que possibilitam que o usuário tenha uma ideia da qualidade geral da obra que desejar através de reviews de outros usuários. Caso queira, o usuário pode também escrever sua própria avaliação de qualquer uma das obras cadastradas no sistema.

Apenas o Administrador do sistema pode cadastrar novos filmes e interagir com os já disponíveis para edita-los ou apaga-los. 

Cada filme tem também a sua respectiva equipe, formada por indivíduos que estão cadastradas no banco de dados na tabela "crewMember", e são nada mais nada menos que as pessoas que trabalharam na produção do filme, seja como atores, diretores, produtores ou cinegrafistas.

Os "crewMember", não são usuários do sistema, apenas figuras cadastradas no banco de dados para serem relacionadas à diversos filmes e então listadas.

### 2.2 Levantamento de requisitos

Os requisitos do sistema foram levantados tendo em vista o objetivo final de gerar um ambiente confiável e fácil de usar, gerando assim uma melhor experiência do usuário (UX). Para isso foram tomados como base sistemas como o Rotten Tomatoes e o IMDb (Ambos sistemas já existentes de avaliações de filmes).

#### 2.2.1 Requisitos Funcionais

Requisitos funcionais descrevem as funcionalidades e ações específicas que um sistema ou software deve realizar, incluindo entradas, processamento e saídas. Eles definem o comportamento funcional do sistema.  
Os requisitos funcionais foram criados em conjunto do grupo que está no desenvolvimento dessa aplicação, e a orientadora, tendo como base pesquisas na web sobre o funcionamento de aplicações como essa. 

No Quadro 1, encontram-se detalhadamente descritos os requisitos funcionais estabelecidos para o Rate It.

Quadro 1 - Requisitos Funcionais do sistema Rate It

| Código | Requisito Funcional                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     | Caso de uso               |
| ------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------- |
| RF 01  | O sistema deve permitir que usuários façam cadastro e  assim tenham acesso ao sistema. O usuário tem os atributos: id, name, login, password, isAdmin (variável booleana que indica se o usuário é administrador ou não).                                                                                                                                                                                                                                                                                                                                                               | UC 01 - Manter Usuário    |
| RF 02  | O sistema deve permitir acesso via login e senha                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | UC 02 -  Gerenciar Acesso |
| RF 03  | Caso o usuário seja administrador, o sistema deve permitir que ele cadastre, edite, remova e liste os filmes do ambiente virtual. Além disso os filmes, que estão cadastrados no banco de dados, devem ter os atributos: id, title, releaseDate, description, genre e runtime.                                                                                                                                                                                                                                                                                                          | UC 03 - Gerenciar Filmes  |
| RF 04  | O sistema deve permitir que o usuário avalie os filmes, sendo que cada usuário pode avaliar um filme apenas uma vez, porém vários filmes diferentes, ou seja, um usuário pode fazer várias avaliações, desde que cada uma dela esteja relacionada a um filme diferente. Cada avaliação pode ter apenas um usuário e um filme atrelado, e no banco de dados  a avaliação possui os seguintes atributos: id, rate (nota), title, comment, user_id, movie_id.                                                                                                                              | UC 04 - Manter Avaliações |
| RF 05  | Já foi dito anteriormente que cada filme tem uma equipe (crew), composta por diversos atores, diretores e cineastras cadastrados em uma tabela "crewMember" no banco de dados, sendo que cada indivíduo pode estar em vários filmes e vários filmes podem ter vários indivíduos, inclusive repetidos ao longo de diferentes filmes, ou seja, uma relação n para n. Esse "crewMember" também será gerenciado pelo administrador do sistema, que por sua vez pode adicionar, editar, remover e listar registros. os crew members tem os seguintes atributos: id, name, jobTitle, picture. | UC 05 - Gerenciar Crew    |

#### 2.2.2 Regras de Negócio

As regras de negócio aqui levantadas são diretrizes que delimitam e orientam o funcionamento do sistema.

Quadro 2 - Regras de Negócio do sistema Rate It

| Código | RF    | Regra de Negócio                                                                                                                                                          |
| ------ | ----- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| RN 01  | RF 01 | Qualquer usuário pode se cadastrar no sistema.                                                                                                                            |
| RN 02  | RF 03 | Apenas o administrador do sistema pode gerenciar os filmes.                                                                                                               |
| RN 03  | RF 04 | Qualquer usuário pode avaliar qualquer filme cadastrado no sistema, sendo que cada usuário pode fazer várias avaliações de filmes diferentes, uma para cada filme apenas. |
| RN 04  | RF 05 | Apenas o administrador do sistema pode gerenciar os "crewMembers".                                                                                                        |
| RN 05  | RF 05 | Cada "crewMember" pode estar em vários filmes diferentes.                                                                                                                 |

#### 2.2.3 Requisitos Não Funcionais Tecnológicos

Os requisitos não funcionais tecnológicos do sistema foram escolhidos a partir da consideração do desenvolvimento e manutenção futura do sistema, compreendendo que cada linguagem de programação, framework e SGBD (Sistema de Gerenciamento de Banco de Dados) utilizado tem suas vantagens e limitações.

Quadro 3 - Requisitos Não Funcionais Tecnológicos do sistema Rate It

| Código  | Requisito Não Funcional Tecnológico                                       |
| ------- | ------------------------------------------------------------------------- |
| RNFT 01 | JavaScript (ES2021) como linguagem de programação principal.              |
| RNFT 02 | O framework React JS e JSX para estruturação do Front-end.                |
| RNFT 03 | Node com npm como ambiente de execução da API Backend.                    |
| RNFT 04 | PostgreSQL 11 para gerenciamento do banco de dados.                       |
| RNFT 05 | Git e GitHub para versionamento e armazenamento do código e documentação. |

## 3 Diagramas de análise e modelagem do sistema

Os diagramas são modelos visuais que ajudam a compreender a estrutura e funcionamento do sistema, desde partes isoladas até como um todo. São essenciais na Engenharia de Software por facilitarem o entendimento do sistema e comunicação entre os membros de a equipe de desenvolvimento.

### 3.1 Diagrama de Entidade Relacionamento

O diagrama de Entidade Relacionamento é um tipo de modelo visual que ajuda a compreender a estrutura do banco de dados através de entidades que representam as tabelas do banco, cada uma com seus devidos atributos, e também os relacionamentos entre as tabelas.

![[RateItERD.png]]