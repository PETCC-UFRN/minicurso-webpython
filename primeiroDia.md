---
layout: layoutConteudo
title: Minicurso de Spring
---

<div id="sumario" class="sumario-git">

    <h1>Dia 1</h1>

    <details>
        <summary><a href="#revisando-java">Revisando Java</a></summary>
        <ul>
            <li><a href="#classes-e-objetos">Classes e Objetos</a></li>
            <li><a href="#encapsulamento">Encapsulamento</a></li>
            <li><a href="#organizando-código-em-java">Organizando Código em Java</a></li>
            <li><a href="#verificação-e-testes">Verificação e testes</a></li>
        </ul>
    </details>
    <details>
         <summary><a href="#introduzindo-o-spring">Introduzindo o Spring</a></summary>
        <ul>
            <li><a href="#ecossistema-spring">Ecossistema Spring</a></li>
            <li><a href="#entendendo-dependências">Entendendo Dependências</a>
                <ul> 
                    <li><a href='#spring-como-injetor-de-dependências'>Spring como Injetor de Dependências</a>
                        <ul>
                            <li><a href='#applicationcontext'>ApplicationContext</a></li>
                            <li><a href='#bean'>Bean</a></li>
                            <li><a href='#annotations'>Annotations</a></li>
                            <li><a href='#applicationproperties-ou-yml'>Applicationproperties ou yml</a></li>
                        </ul>
                    </li>
                </ul>
            </li>
            <li><a href="#spring-initialzr">Spring Initialzr</a></li>
            <li><a href="#gerenciadores-de-projeto">Gerenciadores de Projeto</a>
                <ul> 
                    <li><a href="#maves">Maven</a></li>
                    <li><a href="#gradle">Gradle</a></li>
                </ul>
            </li>
            <li><a href="#criando-um-projeto-pela-primeira-vez">Criando um Projeto Pela Primeira Vez</a></li>
            <li><a href="#praticando-a-camada-model">Praticando a Camada Model</a></li>
            <li><a href="#visualizando-resultados-na-prática">Visualizando Resultados na Prática</a></li>
        </ul>
    </details>

  <button class="toggle-button" id="toggle-button">
  
      Esconder Sumário
  
  </button>

</div>

<br>

# Resumo do primeiro dia

Bem vindo ao minicurso **Introdução ao desenvolvimento back-end com Python!**

Esta é a primeira aula do nosso curso. Portanto, será uma aula mais introdutória. Começaremos com uma introdução à Web e a APIs seguida pela preparação do ambiente virtual de Python. Logo após, vamos acompanhar o passo a passo para se criar o primeiro servidor e rodar uma aplicação na Web, bem como gerar e compreender a documentação sobre ela. Por fim, encerraremos a aula com um exercício no qual vocês construirão uma calculadora API utilizando parâmetros de rota. Boa aula!

# O Básico de desenvolvimento web

Quando acessamos um site ou um aplicativo, estamos interagindo com um sistema que, na maioria das vezes, é dividido em duas partes principais que se comunicam entre si: o Front (à frente) e o Back (atrás).

## Front-End (O lado do Cliente)

É a interface gráfica: tudo aquilo que o usuário vê, clica e interage; telas, botões, formulários, animações e o design da página. Geralmente, é construído com HTML, CSS e JavaScript (junto a ferramentas como React, Angular ou Vue).

## Back-End (O lado do Servidor)

É o responsável por processar as regras de negócio, buscar ou salvar informações no banco de dados, garantir a segurança, autenticar usuários e devolver a informação processada para o Front-End exibir. É exatamente no Back-End que o Python atua!

## O que é um Framework?

Um Framework é um conjunto de códigos, bibliotecas e padrões de arquitetura pré-prontos que servem como um esqueleto ou fundação para o seu projeto.

### Por que usar um framework?

- Produtividade: Funcionalidades complexas e repetitivas, como conectar ao banco de dados, configurar rotas web ou lidar com segurança, já vêm prontas ou semi-prontas.
- Padronização: Um framework impõe uma estrutura lógica. Isso ajuda a manter um padrão de código organizado.
- Segurança e Estabilidade: Frameworks de mercado são utilizados e testado.
- Foco no Conteúdo: m vez de gastar dias configurando servidores e conexões, você pode gastar seu tempo programando funcionalidades da sua aplicação.

O framework em Python com o qual trabalharemos ao longo deste minicurso se chama _fastapi_.

## API RESTful

### O que é uma API?
Uma interface de programação de aplicação (API) age como um intermediador entre o cliente (Front) e o servidor (Back), facilitando a sua comunicação e a troca de dados.

### REST

A Transferência Representacional de Estado (REST) nada mais é do que uma arquitetura que impõe condições sobre como uma API deve se comportar. É chamada de RESTful uma API que segue as diretrizes REST:

- **Cliente envia requisição para a API:** O cliente faz uma requisição à API com informações como o método HTTP, parâmetros, etc.;
- **API processa o pedido:** A API valida a requisição e determina a operação lógica necessária de acordo com as informações fornecidas;
- **API se comunica com o Backend:** A API interage com a lógica, o banco de dados ou outros serviços da aplicação para processar a requisição e obter os dados de retorno;
- **API envia resposta ao cliente:** A API retorna o resultado ao cliente, normalmente com um código de status HTTP e os dados de resposta em um formato como JSON ou XML.

Em breve, tocaremos nos tópicos dos códigos de status HTTP e no formato JSON. Aguenta aí!

Os quatro **métodos principais** que indicam requisições de um cliente a uma uma API RESTful, que originam do HTTP, são:

- **GET:** Acessar um recurso do servidor;
- **POST:** Enviar um recurso ao servidor;
- **PUT:** Atualizar um recurso existente no servidor;
- **DELETE:** Remover um recurso do servidor.

## Formato JSON
A Notação de Objeto de JavaScript (JSON) é um dos mais difundidos e suportados formatos de armazenamento e transmissão de dados estruturados. Tem grande facilidade de leitura e escrita tanto por programas quanto por humanos e é o padrão para o framework que utilizaremos.