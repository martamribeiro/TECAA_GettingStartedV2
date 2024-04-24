---
title: "Customização"
description: "List of some customization perks Doks has to offer."
summary: ""
date: 2024-04-18T11:33:24+01:00
lastmod: 2024-04-18T11:33:24+01:00
draft: false
weight: 999
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

Esta página é dedicada a mostrar-te o poder da personalização do Doks. Todas as funcionalidades abaixo foram usadas no desenvolvimento deste site. Podes também visitar a [Documentação do Doks](https://getdoks.org/docs/start-here/getting-started/) para obter mais informações e recursos disponíveis que não acabamos por ulilizar.

Como o Doks é um tema ainda em desenvolvimento, os recursos de documentação ainda são bastante escassos.

## O sistema Doks
A personalização no Doks é feita através da pasta `assets/scss`, disponíveis após o primeiro build feito do projeto:
- `_variables.scss`: Como o nome sugere, este ficheiro é usado para declarações de variáveis para posterior uso e também para evitar a repetição de estilos no ficheiro principal de personalização. O Doks já traz consigo algumas variáveis personalizadas como <b>$primary</b>, mas dá a liberdade de criar variáveis personalizadas ao utilizador.
- `_custom.scss`: Este é o ficheiro principal para definição dos estilos personalizados. Tanto convenções CSS e SCSS são suportadas. Além disso, ele também tem acesso às variáveis criadas e presentes no ficheiro `_variable.scss`. O Doks também permite a criação de ficheiros .scss adicionais que podem ser acoplados a este ficheiro principal.

{{<callout context="note" icon="info-circle">}} O Doks permite <i>override</i> de qualquer varíavel existence no styles. {{</callout>}}

## Fontes
O Doks permite personalização básica de fontes como o tipo de fonte e o peso/tamanho associado aos diferentes elementos presentes nas páginas.
O tema faz uso de dois métodos para definição de fontes:
- Fontes do sistema
- Fontes do Google

### Fontes do sistema
O uso de fontes do sistema (system fonts) garante um carregamento mais rápido da documentação, pois não requer tempo e largura de banda extras para baixar ficheiros externos de fonte.

Para adicionar system fonts ao projeto, basta adiciona-las ao ficheiro `assets/scss/common/_variables-custom.scss`:
```scss
// Escolher todas as fontes reconhecíveis pelo Doks aquando deployment
$font-family-sans-serif:  "Noto Sans", "Liberation Sans", Arial, sans-serif;
```

### Fontes do Google
Como alternativa ao uso de fontes do sistema, Doks oferece o use de fontes do google (Google Fonts). O procedimento recomendado para o devido uso de google fonts será hospedar as fontes no próprio projeto com ferramentas como o google-webfonts-helper ou Fontsource.

Normalmente, as Fontes do Google oferecem uma variedade maior de opções para cada fonte disponível. Varíaveis como o peso de fonte inicial, tipo de fonte (com serifa ou sem), tipo de conjunto de caracteres e muito mais. As Fontes do Google oferecem mais controle desde o início em comparação com as fontes do sistema, que estão limitadas ao que está instalado e carregado previamente.

Por exemplo, tentemos usar a fonte "Montserrat":
1. Visite o google-webfonts-helper e selecione Montserrat. Há uma boa quantidade de escolhas disponíveis. Por agora seguimos com "latino" como charset, "regular" e "500" como peso.
2. Copie o CSS (usando apenas o prefixo /fonts/montserrat) e cole no `assets/scss/common/_custom.scss`:
```scss
// Altera o peso da fonte consoante o pretendido.
/* montserrat500-regular - latin */
@font-face {
  font-display: swap; /* https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-display para mais opções. */
  font-family: 'Montserrat';
  font-style: normal;
  font-weight: 500;
  // mudar url para a localização onde a fonte irá ser guardada
  src: url('../fonts/montserrat-v26-latin-regular.woff2') format('woff2'); /* Chrome 36+, Opera 23+, Firefox 39+, Safari 12+, iOS 10+ */
}
```
3. Baixa os arquivos, extraia-os e copia as fontes em `static/fonts/montserrat/`
4. Adicione a fonte a `assets/scss/common/_variable-custom.scss`:
```scss
// Escolher todas as fontes reconhecíveis pelo Doks aquando deployment
$font-family-sans-serif:  "Montserrat", "Noto Sans", "Liberation Sans", Arial, sans-serif;
```
5. Pré-carregue as fontes para evitar problemas de Cumulative Layout Shift: copie para `node_modules/@hyas/doks-core/layouts/partials/head/resource-hints.html` para `layouts/partials/head/resource-hints.html` e adicione a fonte:
```html
<link rel="preload" href="{{ "fonts/montserrat/montserrat-v26-latin-regular.woff2" | absURL }}" as="font" type="font/woff2" crossorigin>
<link rel="preload" href="{{ "fonts/montserrat/montserrat-v26-latin-500.woff2" | absURL }}" as="font" type="font/woff2" crossorigin>
```

### Tamanho da fonte
O Doks possui uma boa quantidade de variáveis personalizadas para uso imediato, mas ainda dá o poder de criação de estilos personalizados que podem ser escritos em SCSS ou CSS. Podemos usar os poderes do Doks para facilitar o desenvolvimento e manter um tema de design consistente para as páginas do website.

Como mencionado anteriormente, podes definir variáveis para o tamanho da fonte no ficheiro `_variables-custom.scss`, ou simplesmente escrever diretamente no `_custom.scss`.

Um exemplo simples seria:
```scss
// set ao tamanho da fonte normal
:root {
  --base-font-size: 1.5rem;
}
```
```scss
// tamanho de h1 com base na variável definida em _variables-custom.scss
h1 {
  font-size: calc(var(--base-font-size) + 1.5vw);
}

// tamanho de h2 definido diretamente
h2 {
  font-size: 2rem;
}
```

As fontes normalmente vêm com valores de peso específicos, como [Fontes do Google](#fontes-do-google) menciona. Ainda assim, o Doks permite alterações ao peso da fonte com CSS simples:
```scss
// mudar o peso da fonte atual
:root {
  font-weight: 700; // mudar para o peso pretendido
}
```

### Tema de cores
Editar o tema de cores no Doks acaba por possuir o mesmo funcionamento já falado anteriormente, ou seja, definição de varíaveis em `_variables-custom.scss` e definição de styles no ficheiro `custom.scss`.

Assim como a personalização de fontes, podes definir variáveis predefinidas que ajudam a manter uma aparência consistente. O tema do Doks já vem com variáveis predefinidas que também podes usar em conjunto com as tuas próprias variáveis:
```scss
// mudar cor de link quando se passa o rato sobre um link
a:hover {
  color: #b5dec8;
}
```

Tens total liberdade para o que mudar o que desejares. Mais ainda, incetivamos que explores e experimentes com as diferentes capacidades de customização do doks.

{{<callout context="tip" title="Verifique seu HTML">}}
Verifica o arquivo HTML gerado quando desejares alterar uma parte muito específica do documento do doks. Junto com o material de escrita, o HTML também contém todas as classes que ele usa para os styles. Usa essas classes para desvendar ainda mais poderes de customização.
{{</callout>}}

## Shortcodes

O Doks suporta o uso de shortcodes nos seus Markdowns.

Shortcodes são uma maneira simples de incorporar HTML com Markdown. Para usar um shortcode, encapsula o elemento HTML desejado dentro de `{{}}`.

Os shortcodes podem oferecer uma variedade de funcionalidades, embora o doks os use principalmente como links de navegação.

Existem muitos tipos de shortcodes específicos, que cobriremos neste guia.

{{<callout context="note">}}
Podes seguir um guia mais detalhado de shortcodes em [Doks: Shortcodes](https://getdoks.org/docs/basics/shortcodes/).
{{</callout>}}

### Callouts
Os Callouts são usados para fornecer informações adicionais, como notas ou avisos que o usuário deve levar em consideração.

Os destaques podem ser criados com tags de `title`, `context` e `icon`. Os callouts dividem-se em quatro diferentes contextos: `note`, `tip`, `warning` e `caution`.

{{<callout context="note" title="Note" icon="info-circle">}}
Usado para notas adicionais.
{{</callout>}}
{{<callout context="tip" title="Tip" icon="rocket">}}
Usado para dicas extras interessantes que você possa querer dar
{{</callout>}}
{{<callout context="caution" title="Caution" icon="alert-triangle">}}
Alerta o usuário sobre um possível bug ou obstáculo.
{{</callout>}}
{{<callout context="danger" title="Danger" icon="alert-octagon">}}
Alerta o usuário sobre possível problema.
{{</callout>}}

A sintaxe básica para callouts expressa-se como:
```html
<callout context title icon></callout>
```

O doks permite uma personalização completa destes elementos se desejado. Porém, visto que estes elementos possuem situações de uso bastante específicas, alterações grandes aos estilos dos mesmos não é recomendável.

### Details
O elemento de details funciona como um container clicável, que quando clicado oculta ou mostra informações adicionais, que podem ser personalizadas para diferentes fins. Pode funcionar de forma semelhante a notas, ou pode funcionar como um hub de links de navegação que vincula todos os cabeçalhos na página. É até mesmo possível criar um "mini-markdown" dentro destes elementos. A decisão do que colocar nos diversos elementos do doks é deixada à liberdade do utilizador.

A sintaxe básica de um elemento de details é `<details "Título"></details>`.

Por padrão, os elementos details inicializam em um estado fechado. Podes alterar essa propriedade através da flag `open`.

Um exemplo de um elemento de details seria:

{{<details "Exemplo de Details" >}}
Escolhe a mensagem que desejas transmitir...

Cria caixas de código se desejar...
```html
<div></div>
```

Ou navegua pelo site com links.

[Volte ao topo](#top)
{{</details>}}

### Tabs

As tabs são uma boa maneira de organizar informações quando precisamos de diferenciar algum texto ou código por exemplo. Um uso perfeito para esse elemento serão processos de instalação. Como frequentemente a instalação de software depende do sistema operacional, podes criar um elemento de tabs com abas para cada sistema operativo que precises.

Novamente, o doks dá total liberdade ao uso destes elementos.

Para usar tabs, deves criar um elemento `tabs` seguido pelo número de elementos `tab` desejados. Podes associar um título tanto para o elemento tabs quanto para os elementos tab. A criação de tabs deve ser feita da seguinte forma:

```html
<!--Não te esqueças de encapsular os elemento abaixo dentro de {{}} nos teus markdowns-->
<tabs "Tabs Body Title">
  <!--Podes criar a quantidade de elementos tab que desejares-->
  <tab "Tab Title">
    Content of the tab
  </tab>
</tabs>
```

Um exemplo de um elemento de tabs seria:
{{<tabs "Langague compilers">}}
{{<tab "C++">}}
  ```bash
  g++ main.cpp -o main
  ./main.exe
  ```
{{</tab>}}

{{<tab "Rust">}}
  ```bash
  rustc main.rs
  ./main.exe
  ```
{{</tab>}}

{{<tab "Go">}}
  ```bash
  go build
  main.exe
  ```
{{</tab>}}
{{</tabs>}}

### Link Cards

Os Link Cards oferecem uma forma elegante de design para links de navegação, tanto para links externos como internos.

A sintaxe para usar esses links é definida como `<link-card title description href target>`. Os link cards requerem que sejam definidos os atributos `title` e  `href`. Opcionalmente, também podes definir uma descrição (atributo `description`) ou outros atributos normais de um link como `target`.

{{<link-card
  title="Link Card example"
  description="Let's go back to the top of the page with this"
  href=#top
>}}

```html
<!--Podes redirecionar o utlizador tanto para headers dentro da página, como para outro página do website ou para outro site por completo-->
<!--Ao colocar o atributo target como '_blank', faz com que quando o utilizor clicar no link card, uma nova aba do browser seja aberta-->
<link-card title="Link Card example" description="Let's go back to the top of the page with this" href=#top>
```

### Card Grids

Como o nome sugere, as card grids ajudam na organização de link cards seguindo um layout de grid horizontal.

A sintaxe usada é `<card-grid></card-grid>`, onde card-grid pode conter vários elementos do tipo link-card, semelhante ao que vimos em [Tabs](#tabs).

{{<card-grid>}}
  {{<link-card title="Doks Website" href="https://getdoks.org/" target="_blank">}}
  {{<link-card title="Go to Link Cards" href="#link-cards">}}
{{</card-grid>}}

```html
<card-grid>
  <link-card title="Doks Website" href="https://getdoks.org/" target="_blank">
  <link-card title="Go to Link Cards" href="#link-cards">
</card-grid>
```

### Como esta página foi feita

A página faz uso dos diferentes tópicos já discutidos.

Ela faz uso abundante de blocos de código, para tornar a documentação mais prática e mais interativa com o usuário.

Também segue as diretrizes de design universal do site, definidas pelas cores utilizadas, estrutura e tamanhos/pesos.

Finalmente, ela faz uso de callouts para funcionar principalmente como notas para o usuário levar em consideração.

Além disso, todos os outros elementos foram usados para fins de ensino.
