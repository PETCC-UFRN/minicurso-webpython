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

[imagem de esquema de API]

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

[esquema dos métodos]

## Formato JSON
A Notação de Objeto de JavaScript (JSON) é um dos mais difundidos e suportados formatos de armazenamento e transmissão de dados estruturados. Tem grande facilidade de leitura e escrita tanto por programas quanto por humanos e é o padrão para o framework que utilizaremos.

[imagem mostrando o formato]

## Códigos de Status HTTP
Códigos de status de resposta HTTP indicam o status de conclusão de uma requisição HTTP específica:

- **200 - OK:** Indica que a requisição obteve êxito;
- **400 - BAD REQUEST:** Indica que o servidor não pôde processar a requisição devido a um erro por parte do cliente; comumente, ocorre devido a sintaxe mal escrita da requisição;
- **404 - NOT FOUND:** Indica que o servidor não pôde encontrar o recurso requisitado pelo cliente;
- **500 - INTERNAL SERVER ERROR:** Indica que o servidor se deparou com uma condição inesperada que o impediu de cumprir a requisição; é a resposta genérica para problemas no o servidor.

# Preparação do Ambiente Python
Com a introdução básica aos conceitos do desenvolvimento web apresentada, é hora de começar os preparativos para se criar o seu primeiro servidor!

## Virtual Environment (venv)
Para se trabalhar em um projeto de Python, é uma excelente prática organizar um ambiente virtual dedicado ao projeto. Essencialmente, uma ambiente virtual é uma instância do (ou link ao) executável do Python que fica guardadinha em uma pasta dentro do diretório do projeto.

Uma vez que o *venv* está ativo, quaisquer módulos de Python instalados serão associados somente ao *venv* daquele projeto, sem interferir com a instalação base do Python ou com qualquer outro projeto.

Isso é importante para evitar conflitos entre módulos que você poderia estar usando em projetos diferentes e para organizar as dependências necessárias para cada um deles, o que também facilita na reprodução do projeto em outra máquina.

### Linha de comando:
```
mkdir novo_projeto
cd novo_projeto
python3  -m venv .venv
source ./.venv/bin/activate
```
Isso cria um diretório para seu projeto e, em seguida, um subdiretório que contém o *venv*. Após rodar o último comando, o ambiente virtual é ativado e se torna possível utilizar comandos *python* e *pip*, necessário para instalar os módulos requisitados.

Para desativar o *venv*, apenas digite:
```
deactivate
```
### VS Code
Para selecionar o *venv* apropriado para seu projeto dentro do VS Code, primeiro abra no VS Code o diretório em que estará o seu projeto e crie a pasta *.venv* pelo comando no terminal:
```
python3 -m venv .venv
```
Em seguida, crie um arquivo *.py* qualquer (*main.py*, por exemplo) para checar o *venv* no canto inferior direito do aplicativo:

[print com seta apontando ao botão]

Normalmente, o VS Code deve detectar o intérprete que já está dentro da pasta *.venv* que vocẽ acabou de criar. Mas, caso o intérprete selecionado pelo editor não seja o deste projeto, basta clicar no botão e escolher o correto.

[print da interface de escolha de intérprete]

Daqui em diante, considere que todos os comandos estão sendo rodados dentro do *venv* do projeto.

# Instalando Dependências
Para este minicurso, trabalharemos com a API fornecida pelo módulo de Python chamado ***fastapi*** e a interface de servidor ***uvicorn***.

Para nossa conveniência, ambos podem ser instalados com um único comando:

```
pip install “fastapi[standard]”
```

Agora, você poderá trabalhar com o *fastapi* e o *uvicorn* no seu projeto.

# Hello, Web!

Com a introdução básica aos conceitos do desenvolvimento web apresentada, é hora de criar seu primeiro servidor!

A base do servidor, convencionalmente, fica em um arquivo chamado *main.py*. Crie-o, seja pela linha de comando ou pelo VS Code.

Primeiro de tudo, já que precisaremos do *fastapi*, temos que importá-lo no início do código. Especificamente, a função FastAPI, que será utilizada para criar a aplicação. Em seguida, para criá-la, basta declarar uma variável *app* e atribuir a ela a função FastAPI:
```
from fastapi import FastAPI

app = FastAPI()
```
[TODO: trocar por foto do código no VS Code]

E, simples assim, sua aplicação foi criada! Essa variável, *app*, será o objeto central do servidor e será chamada em quase todas as partes do código.

No entanto, a aplicação está vazia. Para que o servidor funcione, de fato, é preciso definir as suas rotas ao longo do código, isto é, o que o servidor deve retornar ao cliente para uma determinada requisição. O programador define o que cada rota retorna por meio de uma função, naturalmente, mas é preciso **decorar a função primeiro**.

## Decoradores de Função
Um decorador de função é, na verdade, uma função que recebe outra função como parâmetro e retorna uma nova versão da função que recebeu, com seu comportamento alterado, ou **decorado**.

No nosso contexto, decoradores são utilizados sobre funções que querem retornar algo a ser mostrado ao cliente para definir qual rota leva até elas. O decorador em questão é o método get() de um objeto FastAPI:
```
app.get("/rota/a/seguir")
```

Para aplicar um decorador sobre uma função, basta escrevê-lo na linha acima da sua declaração, acompanhado de um @:
```
@app.get("/postagens")
def mostrar_postagens():
    return ...
```

O exemplo acima faz o seguinte: quando um cliente acessar a rota /postagens/ do servidor, ele mostra ao cliente o retorno da função mostrar_postagens.

## Criação da Primeira Rota
De volta ao nosso código, vamos criar a sua primeira rota! Claramente, deve ser a rota de mais baixo nível do servidor, a "root", por assim dizer, que é a rota "/", comumente chamada de "home". É, essencialmente, a página inicial do servidor.

Com o que vimos sobre decoradores logo acima, ficou fácil declarar a primeira rota:
```
@app.get("/")
def home():
    return {"message": "Hello, Web!"}
```
[TODO: trocar por print do código no VS Code]

Com isso, cada cliente que acessar a página inicial do seu servidor vai receber o seu "Hello, Web!". Note que o retorno da função é um dicionário de Python, um contêiner que, basicamente, tem a mesma sintaxe do formato JSON. Essa conversão de dicionário para JSON é feita automaticamente, de modo que os dados que o cliente recebe já chegam nesse formato.

## Rodando a Aplicação
A melhor forma de ver se suas rotas estão funcionando é checar por conta própria como cliente. Então, é hora de colocar o servidor no ar!

Para fazer isso, utilizaremos o *uvicorn*, a outra dependência que instalamos junto ao *fastapi*. No diretório do projeto, execute o comando do *uvicorn* no terminal:
```
fastapi dev main.py
```
O comando basicamente está dizendo ao *uvicorn* para hostear um servidor usando o *fastapi*, no modo desenvolvedor e baseado no que está escrito no *main.py*.

Agora, seu servidor está sendo hosteado localmente em http://127.0.0.1:8000. Ao abri-lo no navegador, você deve receber a mensagem que enviou para a web!

[foto do hello web no navegador]

Perceba, ainda, que é possível observar no terminal os códigos de status HTTP das requisições que você está fazendo.

[foto dos códigos HTTP no terminal]

Agora, tente mudar alguma coisa no seu código e observe o terminal: a cada vez que você realiza uma mudança, o servidor reinicia para incorporá-la. Isso se deve ao parâmetro "dev", que você passou no comando para rodá-lo. Esse comportamento de recarregamento automático ajuda a agilizar a produção, mas, se você não quiser que o servidor reinicie a cada mudança, basta rodar o comando sem a parte "dev".

Agora que podemos facilmente ver o resultado das nossas funções no servidor, aproveito para demonstrar que é possível retornar dicionários previamente declarados no código, como no exemplo a seguir:
```
# Suponha que o site tem uma seção de postagens feitas por usuários

posts: list[dict] = [
    {
        "id": 1,
        "autor": "Luis Filipe",
        "titulo": "Eu amo o FastAPI",
        "conteudo": "Esse framework é bem fácil de se usar!,
        "data_postagem": "05/11/2026",
    },
    {
        "id": 2,
        "autor": "André Gomes",
        "titulo": "Python é excelente para desenvolvimento web",
        "conteudo": "Python é uma ótima linguagem para desenvolvimento web, especialmente com o FastAPI.",
        "data_postagem": "06/07/2026",
    },
]

# Essa função retorna todos os posts ao cliente que requisitar a rota "/api/posts"
@app.get("/api/posts")
def get_posts():
    return posts
```
[TODO: trocar por print do código no VS Code]

Se você navegar até a rota dessa função, ou seja, http://127.0.0.1:8000/api/posts , você deve encontrar os dados que criou.

[foto dos "posts"]

## Swagger - Documentação Automática
Para facilitar a organização do projeto, o servidor do *uvicorn* conta com uma característica bastante útil: ele gera uma documentação automática sobre todas as rotas da sua aplicação. Essa documentação fica em uma rota própria: "/docs".

Ou seja, acessando http://127.0.0.1:8000/docs, você deve se deparar com a interface do Swagger, o gerenciador da documentação das rotas.

[print da GUI do swagger]

Se você integrou os dois exemplos ao seu código, só deve haver duas rotas no menu. Ao clicar em uma delas, você tem acesso a várias informações úteis, como os códigos de status que ela retorna e seus parâmetros (algo que veremos logo, logo). O botão "Try it out" pode ser clicado para simular uma requisição de cliente para aquela rota, te permitindo ver o que ela retorna ao cliente.

[foto do try it out em ação]

Essencialmente, o Swagger é um grande hub para te ajudar no desenvolvimento da aplicação por conter todas as informações importantes sobre suas rotas em um único lugar, com fácil capacidade para testá-las. Novamente, ele gera a documentação automaticamente, então cada nova rota que você definir no código irá aparecer nele!

# Parâmetros de Rota
Imagine, agora, que vocẽ quer receber os dados de uma postagem em específico. Com o que aprendemos até agora, isso só seria possível ao escrever uma função individual para cada uma das postagens. Então, para facilitar a vida do programador, existem os parâmetros de rota.

Parâmetros de rota te permitem incorporar um valor variável em uma rota, que é passado como parâmetro para a sua função. Com isso, você é capaz de criar uma única rota que responde a uma grande variedade de entradas, reduzindo a necessidade de se criar rotas idênticas, assim como pode retornar recursos ou dados específicos, dependendo do parâmetro de rota recebido.

Para declarar um **parâmetro de rota** no decorador da sua função, escreva-o entre chaves. Para usá-lo na função de fato, passe-o como parâmetro para ela:
```
# No decorador, o parâmetro fica entre chaves
@app.get("/api/posts/{post_id}")
def get_post(post_id: int): # Na função, ele deve ter o mesmo nome
    for post in posts:
        if post["id"] == post_id:
            return post
```

O exemplo acima recebe um valor inteiro *post_id* como parâmetro de rota e retorna ao cliente os dados sobre a postagem cujo *id* é igual ao *post_id*. **Note que é necessário definir o tipo do parâmetro como inteiro**, por dois motivos:

- Isso permite que o FastAPI realize automaticamente a validação para essa rota, de modo que um cliente que tente acessá-la com um parâmetro que não se converte em inteiro, como "api/posts/minicurso" recebe um erro de validação em seu lugar, já que {minicurso} não é um inteiro;
- A própria função precisa saber que o parâmetro é um inteiro pois, senão, vai tratá-lo, por padrão, como string, o que não funcionaria para nosso caso.



## Testes de Parâmetros no Swagger