---
title: "Por Onde Começar"
description: "Página de Por Onde Começar para guiar o leitor nos primeiros passos para criar seu primeiro site com Hugo, usando o tema Doks."
summary: ""
date: 2024-04-23T15:51:55+01:00
lastmod: 2024-04-23T15:51:55+01:00
draft: false
menu:
  docs:
    parent: ""
weight: 801
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

Nesta página, aprenderá os primeiros passos para criar seu primeiro site com o **Hugo**, usando o **tema Doks**.

## Instale o Hugo e Go

### Hugo

**Comece instalando o Hugo no seu dispositivo.** Ao clicar [neste link](https://gohugo.io/installation/), pode verificar as diretrizes de instalação para macOS, LINUX, Windows, BSD e qualquer outra máquina que possa executar a cadeia de ferramentas do compilador Go.

Após instalar o Hugo, deve executar o seguinte comando:

| Windows | MAC |
| :----: | :----: |
| ``` choco install hugo-extended``` | ``` brew install hugo``` |

Em seguida, verifique a versão que está usando com o seguinte comando:

```bash
hugo version
```

### Go

**Agora é hora de instalar o Go.** Ao clicar [neste link](https://go.dev/dl/), pode instalar a versão do Go que preferir, para o seu sistema operacional.

Em seguida, verifique a versão que está usando com o seguinte comando:

```bash
go version
```

## Crie o seu projeto

**Agora, terá de criar um novo projeto com o tema Doks.**

### Crie um projeto novo

A maneira recomendada de criar um novo projeto Hyas + Doks é executando o comando abaixo no seu terminal, no diretório onde deseja criar o seu projeto:

{{<tabs "doks-one">}}
{{<tab "npm">}}
```bash
npm create hyas@latest -- --template doks
```
{{</tab>}}

{{<tab "pnpm">}}
```bash
pnpm create hyas@latest --template doks
```
{{</tab>}}

{{<tab "Yarn">}}
```bash
yarn create hyas@latest --template doks
```
{{</tab>}}
{{</tabs>}}

Isto criará um novo diretório de projeto com todos os arquivos e configurações necessárias para o seu site.

## Instale as dependências

Faça ```cd``` para o diretório do seu novo projeto e instale as dependências antes de continuar.

{{<tabs "doks-two">}}
{{<tab "npm">}}
```bash
npm install
```
{{</tab>}}

{{<tab "pnpm">}}
```bash
pnpm install
```
{{</tab>}}

{{<tab "Yarn">}}
```bash
yarn install
```
{{</tab>}}
{{</tabs>}}

## Visualize o seu projeto

**Agora que criou o seu projeto, é hora de visualizá-lo.** 
Ao trabalhar localmente, o servidor de desenvolvimento do Hugo permite visualizar o seu trabalho e atualiza automaticamente o seu navegador quando faz alterações. Dentro do diretório do seu projeto, execute o seguinte comando para iniciar o servidor de desenvolvimento:

{{<tabs "doks-three">}}
{{<tab "npm">}}
```bash
npm run dev
```
{{</tab>}}

{{<tab "pnpm">}}
```bash
pnpm dev
```
{{</tab>}}

{{<tab "Yarn">}}
```bash
yarn dev
```
{{</tab>}}
{{</tabs>}}

Isso registrará uma mensagem no seu terminal com a URL da sua pré-visualização local. Abra essa URL para começar a navegar pelo seu site.

**Parabéns, concluiu os primeiros passos para criar o seu primeiro website com o Hugo, utilizando o tema Doks!**

<br>

---

<br>

{{< callout context="note" icon="info-circle" >}}

  ### Como esta página foi feita
  
  Esta Chamada existe com o propósito de explicar como esta página foi criada, conforme solicitado para a disciplina de TECAA.

  {{< details "Cabeçalhos" >}}

  Os cabeçalhos foram estrategicamente utilizados em toda a página "Por Onde Começar" para delinear diferentes seções e orientar os leitores pelo processo de instalação.

  Ao usar cabeçalhos como "Instalar o Hugo e Go", "Crie o seu projeto" e "Visualize o seu projeto", o conteúdo é logicamente organizado, tornando mais fácil para os utilizadores navegar e entender cada etapa envolvida na criação do seu primeiro site com o Hugo e o tema Doks.

  Os cabeçalhos são indicados por um ou mais símbolos de cardinal ```#``` seguidos por um espaço e o texto do cabeçalho. O número de símbolos de cardinal determina o nível do cabeçalho, com um símbolo de cardinal ```#``` representando o nível mais alto (H1), dois símbolos de cardinal ```##``` representando o segundo nível (H2), e assim por diante.

  Exemplo:

  ```bash
  # Header 1
  ## Header 2
  ### Header 3
  ```

  {{< /details >}}

  {{< details "Abas" >}}

  As abas foram utilizadas dentro dos passos de instalação para fornecer instruções separadas para diferentes gerenciadores de pacotes. Essa abordagem garante que os leitores possam acessar rapidamente as instruções relevantes para eles sem serem sobrecarregados por informações desnecessárias.

  As abas são implementadas usando shortcodes. Elas permitem que os usuários alternem entre diferentes conjuntos de informações dentro de uma única seção de conteúdo.

  Exemplo:

  {{< figure
  src="images/tabs_gs.png"
  alt="Imagem a mostrar um excerto de código em que as Abas são implementadas."
  caption="">}}

  {{< /details >}}

  {{< details "Tabelas" >}}

  As tabelas foram incorporadas para apresentar comandos de instalação para diferentes sistemas operacionais. As tabelas permitem uma comparação fácil entre as opções de instalação, permitindo que os usuários escolham o método que melhor se adapta às suas preferências e requisitos.

  Tabelas são criadas usando símbolos de barra vertical ```|``` para separar colunas e hífens ```-``` para definir os cabeçalhos da tabela. Cada linha representa uma entrada separada na tabela, com células separadas por símbolos de barra vertical.

  Exemplo:

  ```bash
  | Windows | MAC |
  | :----: | :----: |
  | ``` choco install hugo-extended``` | ``` brew install hugo``` |
  ```

  {{< /details >}}

  {{< details "Hiperligações" >}}

  Hiperligações foram inseridas estrategicamente em toda a página para fornecer acesso fácil a recursos externos e documentação relevante. Ao incluir hiperligações para a página de instalação oficial do Hugo e a página de download do Go, os utilizadores podem acessar rapidamente informações adicionais e recursos para ajudá-los no processo de instalação.

  Hiperligações são criadas usando a sintaxe ```[link text](URL)```, onde o texto do link representa o texto clicável exibido para os usuários e a URL especifica o destino.

  Exemplo:

  ```bash
  [neste link](https://gohugo.io/installation/)
  ```

  {{< /details >}}

  {{< details "Blocos de Código" >}}

  Blocos de código foram usados para exibir comandos. Ao apresentar comandos de uma maneira estruturada e formatada, os utilizadores podem identificá-los e executá-los facilmente. Além disso, os blocos de código permitem copiar e colar facilmente, permitindo que os utilizadores repliquem os comandos com precisão e eficiência.

  Blocos de código são delimitados por três crases (```).

  Exemplo:

  {{< figure
  src="images/codeblock_gs.png"
  alt="Imagem a mostrar um excerto de código em que os Blocos de Código são implementadas."
  caption="">}}

  {{< /details >}}

  {{< details "Chamada" >}}

  No final da página, uma Chamada foi incluída para explicar como a página foi criada. Esta Chamada fornece informações importantes que podem ser úteis para os utilizadores quando começarem a trabalhar em suas próprias páginas.

  Chamadas são implementadas usando shortcodes personalizados. Elas são usadas para chamar a atenção para informações específicas ou fornecer contexto adicional.

  Exemplo:

  {{< figure
  src="images/callout_gs.png"
  alt="Imagem a mostrar um excerto de código em que a Chamada é implementada."
  caption="">}}

  {{< /details >}}

  {{< details "Figuras" >}}

  Na seção de chamadas, figuras foram incluídas para representar visualmente exemplos de como diferentes elementos foram implementados na página "Por Onde Começar", especialmente aqueles que não puderam ser inseridos dentro de blocos de código, por questões de formatação.

  Exemplo:

  {{< figure
  src="images/figures_gs.png"
  alt="Imagem a mostrar um excerto de código em que a Figura é implementada."
  caption="">}}

  {{< /details >}}

  Ao incorporar estrategicamente cabeçalhos, abas, tabelas, hiperlinks, blocos de código, chamadas e figuras ao longo da página "Por Onde Começar", o conteúdo é organizado, apresentado e explicado de forma eficaz aos utilizadores. Cada elemento serve a um propósito específico ao orientar os utilizadores pelo processo de instalação e fornecer as informações e recursos necessários para criar seu primeiro site com Hugo e o tema Doks.

{{< /callout >}}

<br>

---