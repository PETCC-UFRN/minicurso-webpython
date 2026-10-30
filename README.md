# Repositório Oficial do Site do Minicurso de Desenvolvimento Web com Python - FastAPI
Este é o repositório onde é hospedado o site via GitHub Pages do Minicurso de Desenvolvimento Web com Python - FastAPI. Neste arquivo você verá um tutorial de como utilizar o gerador de páginas estáticas **Jekyll** para alterar os recursos deste projeto.

# Instalando o Jekyll

#### OBS: Esse tutorial cobre a utilização do Jekyll exclusivamente neste projeto. Para um tutorial mais aprofundado visite o site: <https://jekyllrb.com/docs/>

## Requisitos

| Ferramenta | Versão | Como obter |
|----------|----------|----------|
| Ruby | 3.3.3 (Recomendada) | [RubyInstaller](https://rubyinstaller.org/downloads/) (Windows) ou **rbenv** (Linux/macOS) |
| Jekyll e Bundler | Mais recentes | Instalação pelo terminal |

## Instalação do Ruby

A forma de instalar o Ruby varia de acordo com o seu sistema operacional:

### No Windows
1. Acesse o site do [RubyInstaller](https://rubyinstaller.org/downloads/) e instale a versão recomendada (Ruby+Devkit).
2. Siga as instruções padrão de instalação.

### No Linux / macOS (Via `rbenv`)
É fortemente recomendado **não** utilizar o Ruby que vem nativo no sistema ou instalá-lo diretamente via gerenciadores de pacote (como `apt` ou `dnf`), pois isso costuma gerar problemas de permissão (erros de `sudo`) ao instalar *gems*. O ideal é utilizar um gerenciador de versões como o **rbenv**.

1. Instale o `rbenv` e o plugin `ruby-build` seguindo as [instruções do repositório oficial](https://github.com/rbenv/rbenv#installation) (os comandos variam de acordo com a sua distribuição Linux ou macOS).
2. Após configurar o `rbenv` no seu shell, instale a versão recomendada do Ruby e defina-a como a versão global do seu sistema:
   ```bash
   rbenv install 3.3.3
   rbenv global 3.3.3


## Configurando o Projeto

1. Depois de instalar o Ruby, abra um terminal e instale o Jekyll e o Bundler globalmente:
```bash
gem install jekyll bundler

```


2. Navegue até a pasta principal deste repositório e instale as dependências específicas do projeto:
```bash
bundle install

```



## Rodando o site localmente

Sempre que for rodar comandos do Jekyll neste repositório, use o prefixo `bundle exec` para garantir que as versões corretas das dependências estão sendo usadas.

* Para construir os arquivos do site: `bundle exec jekyll build`
* Para hospedar o site localmente: `bundle exec jekyll serve`

Com o comando ***serve*** rodando, qualquer alteração salva nos arquivos do projeto já irá atualizar a página automaticamente no localhost.

---

# Utilizando o Jekyll

## Páginas em Markdown

Usando o Jekyll, é possível criar uma página em Markdown e ela será automaticamente *portada* para HTML usando a ferramenta. Sendo assim, para criar uma página para o site, basta criar um arquivo `.md` no diretório principal do site e alterá-lo como desejar, como se estivesse escrevendo algo no HackMD ou Notion.

Todavia, existem alguns pontos importantes que vão ser abordados abaixo.

## Front Matter

O *front matter* é declarado no início de um arquivo em um projeto Jekyll e pode ser usado para declarar variáveis para aquela página (Exemplo: `titulo_da_pagina: Minicurso de Estruturas de Dados`) e, principalmente, para definir o layout que a página irá usar.

O *front matter* possui o seguinte formato:

```yaml
---
title: Minicurso de Estruturas de Dados
layout: default
---

```

Os hífens são necessários para separar o conteúdo do front matter do resto da página e ele deve ser declarado na primeira linha do arquivo.

## Layouts

Existem 5 layouts nesse projeto até o momento:

* **default**: layout padrão
* **home**: layout da homepage
* **licoes**: layout da página que lista todas as lições
* **sobre**: layout da página que fala sobre o curso
* **oldschool**: em html é o mesmo layout da página de lições, apenas com classes diferentes para mudar a paleta de cores

Para adicionar um novo layout, basta criar um arquivo `.html` na pasta `_layouts` do projeto. Todo o esqueleto da página em HTML vai ser usado na hora de importar uma página Markdown, e a tag `{{ content }}` denota onde o conteúdo exclusivo da sua página Markdown será inserido dentro daquele layout.

## Includes

Os *includes* são arquivos HTML guardados na pasta `_includes` e representam estruturas modulares que podem ser incluídas em qualquer layout. Os *includes* são utilizados para evitar a monotonia de escrever a mesma estrutura inteira em cada layout.

Eles podem ser importados utilizando a tag `{% include arquivo.html %}` no local desejado. Um exemplo de include nesse projeto é o **menu de navegação** que fica no topo do site.

## Assets

Sendo algo em comum para qualquer projeto web, os *assets* do projeto — isto é, as imagens, as folhas de estilo (CSS), as fontes não nativas usadas, etc. — são guardados na pasta `assets/`.

**Atenção:** É importante garantir que as alterações sejam feitas na pasta `assets/` na raiz do projeto, e **não** na pasta `_site/assets` (que é gerada automaticamente pelo Jekyll e será sobrescrita a cada build).

## Outros arquivos importantes

* **Gemfile e Gemfile.lock**: São arquivos do Bundler (Ruby) que especificam as bibliotecas (gems) e as versões exatas que estão sendo usadas neste projeto.
* **_config.yml**: É o arquivo de configuração principal do Jekyll. Nele pode-se alterar o gerador de Markdown (a ferramenta usada para transformar páginas Markdown em HTML), dados globais do site, plugins, entre outras configurações fundamentais do projeto.

```

```
