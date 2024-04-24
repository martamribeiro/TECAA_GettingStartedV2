---
title: "Implantação"
description: "Página de Implantação para orientar os leitores sobre como implantar com sucesso o seu site Hugo."
summary: ""
date: 2024-04-22T12:48:55+01:00
lastmod: 2024-04-22T12:48:55+01:00
draft: false
menu:
  docs:
    parent: ""
weight: 900
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---
---

**Pronto para construir e implantar seu site Doks?** Siga um dos guias disponíveis no HyasDocs para diferentes serviços de implantação ou dê scroll para baixo para obter orientações gerais sobre como implantar um site Hyas.


## Guias de Implantação {#section-1}

{{< card-grid >}}

  {{< link-card
  title="Netlify"
  href="https://docs.gethyas.com/guides/deploy/netlify/"
  target="_blank">}}

  {{< link-card
  title="Vercel"
  href="https://docs.gethyas.com/guides/deploy/vercel/"
  target="_blank">}}

  {{< link-card
  title="GitHub Pages"
  href="https://docs.gethyas.com/guides/deploy/github/"
  target="_blank">}}

  {{< link-card
  title="GitLab Pages"
  href="https://docs.gethyas.com/guides/deploy/gitlab/"
  target="_blank">}}

{{< /card-grid >}}

{{< card-grid >}}

  {{< link-card
  title="Cloudflare Pages"
  href="https://docs.gethyas.com/guides/deploy/cloudflare/"
  target="_blank">}}

  {{< link-card
  title="Firebase Hosting"
  href="https://docs.gethyas.com/guides/deploy/google-firebase/"
  target="_blank">}}

  {{< link-card
  title="Microsoft Azure"
  href="https://docs.gethyas.com/guides/deploy/microsoft-azure/"
  target="_blank">}}

  {{< link-card
  title="Render"
  href="https://docs.gethyas.com/guides/deploy/render/"
  target="_blank">}}

{{< /card-grid >}}


## Opções de Implantação Rápida {#section-2}
Você pode construir e implantar um site Hyas (incluindo um tema Doks) em vários hosts rapidamente usando o painel de controle do site ou um CLI.

### Interface do Website {#section-2.1}

Uma maneira rápida de implantar o seu site é conectar o repositório Git online do seu projeto Hyas (por exemplo, GitHub, GitLab, Bitbucket) a um provedor de hospedagem (host) e aproveitar a implantação contínua usando Git.

Estas plataformas de hospedagem detectam automaticamente os envios para o repositório de origem do seu projeto Hyas, constroem seu site e o implantam na web em um URL personalizado ou em seu domínio pessoal. Frequentemente, configurar uma implantação nestas plataformas seguirá etapas semelhantes às seguintes:

1. Adicione seu repositório a um provedor Git online (por exemplo, no GitHub, GitLab, Bitbucket).

2. Escolha um host que suporte **implantação contínua** (e.g. [Netlify](https://docs.gethyas.com/guides/deploy/netlify/) ou [Vercel](https://docs.gethyas.com/guides/deploy/vercel/)) e importe seu repositório Git como um novo site/projeto. <br>
  <br>Muitos hosts comuns reconhecerão seu projeto como um site Hyas e devem escolher as configurações apropriadas para construir e implantar seu site, como mostrado abaixo. (Caso contrário, essas configurações podem ser alteradas.)
  
  {{< callout context="note" title="Configurações de Implantação" icon="info-circle" >}}
  
  - **Comando de Construção:** `hyas build` ou `npm run build`
  - **Diretório de Publicação:** `public`

  {{< /callout >}}

3. Clique em "Implantar" e seu novo site será criado em um URL único para esse host (e.g. `new-hyas-site.netlify.app`).

<br>O host será automaticamente configurado para observar a branch principal do seu provedor Git em busca de alterações e reconstruir e republicar seu site a cada novo commit. Essas configurações geralmente podem ser configuradas no painel de controle do seu provedor de hospedagem.

### Implantação via CLI {#section-2.2}

Alguns hosts terão sua própria interface de linha de comando (CLI) que você pode instalar globalmente em sua máquina usando o npm. Geralmente, usar uma CLI para implantar se parece com o seguinte:

1. Instale a CLI do seu host globalmente, por exemplo:
  {{< tabs "cli-host-global" >}}
{{< tab "npm" >}}

```bash
npm install --global netlify-cli
```

{{< /tab >}}
{{< tab "pnpm" >}}

```bash
pnpm add --global netlify-cli
```

{{< /tab >}}
{{< tab "Yarn" >}}

```bash
yarn global add netlify-cli
```

{{< /tab >}}
{{< /tabs >}}

2. Execute a CLI e siga quaisquer instruções para autorização, configuração etc.

3. Construa seu site e implante no seu host<br>
<br>Muitos hosts comuns irão construir e implantar seu site para você. Eles geralmente reconhecerão seu projeto como um site Hyas e devem escolher as configurações apropriadas de configuração para construir e implantar conforme mostrado abaixo. (Se não, essas configurações podem ser alteradas.)<br>
  {{< callout context="note" title="Configurações de Implantação" icon="info-circle" >}}
  - **Comando de Construção:** `hyas build` or `npm run build`
  - **Diretório de Publicação:** `public`

  {{< /callout >}}
  Outros hosts exigirão que você [construa seu site localmente](#section-3) e implante usando a linha de comando.

<br>

## Construindo Seu Site Localmente {#section-3}
Muitos hosts, como Netlify e Vercel, construirão seu site para você e, em seguida, publicarão essa saída de construção na web. No entanto, alguns sites exigirão que você construa localmente e, em seguida, execute um comando de implantação ou faça upload da saída de construção.

Você também pode desejar construir localmente para [visualizar seu site](#section-4) ou para identificar quaisquer erros e avisos em seu próprio ambiente.

Execute o comando `npm run build` para construir seu site Hyas.

{{< tabs "cli-host-global" >}}
{{< tab "npm" >}}

```bash
npm run build
```

{{< /tab >}}
{{< tab "pnpm" >}}

```bash
pnpm run build
```

{{< /tab >}}
{{< tab "Yarn" >}}

```bash
yarn run build
```

{{< /tab >}}
{{< /tabs >}}

Por padrão, a saída de construção será colocada em `public/`. Essa localização pode ser alterada usando a [opção de configuração `publishDir`.](https://gohugo.io/getting-started/configuration/#publishdir).

## Visualizando Seu Site Localmente {#section-4}
Ao lado do servidor de desenvolvimento integrado do Hugo, o Hyas vem com o [http-server](https://github.com/http-party/http-server), um servidor HTTP estático simples e sem configuração.

Execute o comando `npm run preview` para visualizar seu site Hyas.

{{< tabs "cli-host-global" >}}
{{< tab "npm" >}}

```bash
npm run preview
```

{{< /tab >}}
{{< tab "pnpm" >}}

```bash
pnpm run preview
```

{{< /tab >}}
{{< tab "Yarn" >}}

```bash
yarn run preview
```

{{< /tab >}}
{{< /tabs >}}

O script `http-server` sé configurado para ser executado com [gzip](https://developer.mozilla.org/en-US/docs/Glossary/GZip_compression), [brotli](https://developer.mozilla.org/en-US/docs/Glossary/Brotli_compression), e [CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS) habilitados. Essas configurações podem ser alteradas usando as [opções disponíveis](https://github.com/http-party/http-server#available-options).


<br>

---

<br>

{{< callout context="note" title="Como esta página foi feita" icon="info-circle" >}}
  
  Este Callout existe com o propósito de explicar como esta página foi criada, conforme solicitado para a disciplina de TECAA.

  #### Seções do Documento
  Como pode ser visto na Tabela de Conteúdos disponível no lado esquerdo da página, este documento está dividido em várias seções. Isso pode ser alcançado em nosso Tema Doks usando cabeçalhos markdown, adicionando `#` antes do texto que desejo tornar um Cabeçalho. Quanto mais `#`  adicionados antes de um texto, define seu tipo. Por exemplo, `# Header1`  define um cabeçalho h1, `## Header2` define um cabeçalho h2, e assim por diante. Nesta página, foi feito o seguinte:

  ```markdown
    ## Deployment Guides {#section-1}
    ## Quick Deploy Options {#section-2}
    ### Website UI {#section-2.1}
    ### CLI Deployment {#section-2.2}
    ## Building Your Site Locally {#section-3}
    ## Previewing Your Site Locally {#section-4}
  ```

  Para cada seção, também foi definido um `{section-x}`. Isso foi implementado para poder referenciar essas seções em hiperlinks, para serem exploradas mais adiante.

  #### Quebras Temáticas (Linhas Horizontais)
Para criar uma linha horizontal para dividir o conteúdo da página ou mesmo o Cabeçalho do texto, como pode ser visto logo após o Título principal da página, pode-se usar três ou mais hífens consecutivos, sublinhados ou asteriscos. Para esta página, `---` (três hífens consecutivos) foram usados para criar as quebras temáticas, como a seguinte:
  
  --- 

  #### Texto em Negrito
Para o texto que pode ser visto em negrito, no meio das frases, isso pode ser alcançado colocando ** antes e depois do texto desejado em negrito. Por exemplo, **este** está em negrito ao fazer `**este**`.

  #### Link Cards
  Para criar a [Development Guides section](#section-1) Link-Cards e Card-Grids foram usados. Esta é a funcionalidade que nossa equipa apresentou no Hands-On para TECAA.
   Cada linha de Link-Cards foi criada usando Card-Grids, e cada coluna dessa linha criada usando Link-Cards, como pode ser visto aqui:

  {{< figure
  src="images/linkcards.png"
  alt=""
  caption="">}}

  #### Hiperligações
  Todas as hiperligações encontradas nesta página foram feitos usando o que é padrão para arquivos markdown, `[Link texto](URL)`.
  Aqui, as hiperligações foram usadas de duas maneiras diferentes:
  1. Para redirecionar para outra página ou site, por exemplo, para a Documentação do Hyas, o seguinte foi feito:<br> `[Netlify](https://docs.gethyas.com/guides/deploy/netlify/)`

  2. Para redirecionar para uma seção dentro desta página, o texto adicionado aos títulos, `{section-x}`, foi usado:<br> `[preview your site](#section-4)`

  #### Listas
Esta página apresenta dois tipos diferentes de listas, ordenadas e não ordenadas.
Para criar as listas ordenadas, presentes em muitas das seções desta página, o seguinte foi feito:

  ```markdown
    1. Item 1
    2. Item 2
    3. Item 3

  ```

  Para criar as listas não ordenadas, em vez de usar números seguidos de um ponto, um hífen foi usado, assim como acontece nos arquivos markdown:

  ```markdown
    - Item 1
    - Item 2
    - Item 3
  
  ```

  #### Callouts
  O uso de Callouts foi uma ideia trazida de um Hands-On apresentado por outra equipa de TECAA. Embora os Callouts não sejam criados da mesma forma neste site com tema Doks, eles fazem o mesmo e parecem semelhantes.
Para criar os Callouts usados nesta página, incluindo o usado para esta seção, o seguinte foi feito:

  {{< figure
  src="images/callout.png"
  alt=""
  caption="">}}

  Ao alterar os seus atributos podemos criar outros tipos de Callouts, alterando a sua cor, título e até mesmo o ícone associado, como pode ser visto nos exemplos abaixo:

  {{< figure
  src="images/callout_examples.png"
  alt=""
  caption="">}}

  #### Formatação de Código Inline
Ao longo desta página, podem ser vistos dois tipos diferentes de formatação para destacar comandos e códigos bash.<br>
Para pequenos trechos de código ou comandos que desejo exibir no meio de uma frase, usei ´ entre o texto para formatar.
Por exemplo, para obter `npm run preview`, fiz o seguinte com backticks:

  ```markdown
    ´npm run preview´
  ```

  Para pedaços maiores de código ou comandos e para criar uma caixa maior como pode ser visto no exemplo acima, existem dois estilos diferentes que podem ser implementados.
Para criar uma caixa semelhante a uma linha de comando bash, fiz o seguinte usando três backticks:
  
  ```markdown
    ```bash
      Text Here
    ```
  ```

  This results in:
  ```bash
    Text Here
  ```

  Para criar uma caixa que se assemelhe e funcione como um arquivo markdown, como a que estou usando aqui, substituí a opção "bash" na fórmula por "markdown":

  ```markdown
    ```markdown
      Text Here
    ```
  ```

  Resultando em:

  ```markdown
    Text Here
  ```

  #### Abas
As abas foram usadas ao longo da página para mostrar os mesmos comandos para diferentes terminais (linhas de comando).
Para criar as abas, usei os shortcodes "tabs" e "tab", como pode ser visto no seguinte exemplo:

  {{< figure
  src="images/tabs.png"
  alt=""
  caption="">}}  

  #### Images
  As imagens usadas ao longo da página e no restante do site estão armazenadas na pasta de "assets" de nosso projeto:

  {{< figure
  src="images/assets.png"
  alt=""
  caption="">}}

  O arquivo `module.toml` acompanha a pasta de "assets":

  {{< figure
  src="images/moduletoml.png"
  alt=""
  caption="">}}

  IAs imagens foram usadas apenas nesta página na seção atual para mostrar linhas de código. As imagens foram implementadas da forma que pode ser vista aqui:

  {{< figure
  src="images/imageexample.png"
  alt=""
  caption="">}}

{{< /callout >}}

<br>

---