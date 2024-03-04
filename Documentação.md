
# Rate It

## Plataforma de avaliação de filmes

**Gabriel dos Santos de Castro**

## Resumo

Rate It é uma plataforma de avaliação de filmes idealizada com o intuito de facilitar a avaliação de filmes catalogados com a finalidade de que o usuário final possa filtrar o que lhe agrada ou não. Os conceitos mais gerais da aplicação envolvem as entidades dos filmes, avaliações, usuários, que também incluem o administrador do sistema e, finalmente, os membros da equipe de cada filme.

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

Cada filme tem também a sua respectiva equipe, que no banco de dados tem o nome "Crew", que são nada mais nada menos que as pessoas que trabalharam na produção do filme, seja como atores, diretores, produtores ou cinegrafistas.

Os membros do "Crew", não são usuários do sistema, apenas figuras cadastradas no banco de dados para serem relacionadas à diversos filmes e então listadas.

### 2.2 Levantamento de requisitos

Os requisitos do sistema foram levantados tendo em vista o objetivo final de gerar um ambiente confiável e fácil de usar, gerando assim uma melhor experiência do usuário (UX). Para isso foram tomados como base sistemas como o Rotten Tomatoes e o IMDb (Ambos sistemas já existentes de avaliações de filmes).

#### 2.2.1 Levantamento de Requisitos Funcionais

Requisitos funcionais descrevem as funcionalidades e ações específicas que um sistema ou software deve realizar, incluindo entradas, processamento e saídas. Eles definem o comportamento funcional do sistema.  
Os requisitos funcionais foram criados em conjunto do grupo que está no desenvolvimento dessa aplicação, e a orientadora, tendo como base pesquisas na web sobre o funcionamento de aplicações como essa. 

No Quadro 1, encontram-se detalhadamente descritos os requisitos funcionais estabelecidos para o Rate It.

Quadro 1 - Requisitos Funcionais do sistema Rate It

| Código | Requisito Funcional                                                                                                                                                                                                                                                                                                                                                                                                                                               | Caso de uso               |
| ------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------- |
| RF 01  | O sistema deve permitir que usuários façam cadastro e  assim tenham acesso ao sistema. O usuário tem os atributos: id, name, login, password, isAdmin (variável booleana que indica se o usuário é administrador ou não).                                                                                                                                                                                                                                         | UC 01 - Manter Usuário    |
| RF 02  | O sistema deve permitir acesso via login e senha                                                                                                                                                                                                                                                                                                                                                                                                                  | UC 02 -  Gerenciar Acesso |
| RF 03  | Caso o usuário seja administrador, o sistema deve permitir que ele cadastre, edite, remova e liste os filmes do ambiente virtual. Além disso os filmes, que estão cadastrados no banco de dados, devem ter os atributos: id, title, releaseDate, description, genre e runtime.                                                                                                                                                                                    | UC 03 - Gerenciar Filmes  |
| RF 04  | O sistema deve permitir que o usuário avalie os filmes, sendo que cada usuário pode avaliar um filme apenas uma vez, porém vários filmes diferentes, ou seja, um usuário pode fazer várias avaliações, desde que cada uma dela esteja relacionada a um filme diferente. Cada avaliação pode ter apenas um usuário e um filme atrelado, e no banco de dados  a avaliação possui os seguintes atributos: id, rate (nota), title, comment, user_id, movie_id.        | UC 04 - Manter Avaliações |
| RF 05  | Já foi dito anteriormente que cada filme tem uma equipe (crew), composta por diversos atores, diretores e cineastras cadastrados em uma tabela "crew" no banco de dados, sendo que cada cineastra pode estar em vários filmes e vários filmes podem ter vários cineastras, inclusive repetidos ao longo de diferentes filmes. Esse crew também será gerenciado pelo administrador do sistema, que por sua vez pode adicionar, editar, remover e listar registros. | UC 05 - Gerenciar Crew    |
 







