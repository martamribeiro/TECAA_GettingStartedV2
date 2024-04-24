---
title: "Deployment"
description: "Deployment page to guide readers on how to succesfully deploy their hugo website."
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

**Ready to build and deploy your Doks site?** Follow one of the guides available on HyasDocs to different deployment services or scroll down for general guidance about deploying a Hyas site.


## Deployment Guides {#section-1}

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


## Quick Deploy Options {#section-2}
You can build and deploy a Hyas site (including a Doks themed one) to a number of hosts quickly using either their website’s dashboard UI or a CLI.

### Website UI {#section-2.1}

A quick way to deploy your website is to connect your Hyas project’s online Git repository (e.g. GitHub, GitLab, Bitbucket) to a host provider and take advantage of continuous deployment using Git.

These host platforms automatically detect pushes to your Hyas project’s source repository, build your site and deploy it to the web at a custom URL or your personal domain. Often, setting up a deployment on these platforms will follow steps something like the following:

1. Add your repository to an online Git provider (e.g. in GitHub, GitLab, Bitbucket)

2. Choose a host that supports **continuous deployment** (e.g. [Netlify](https://docs.gethyas.com/guides/deploy/netlify/) or [Vercel](https://docs.gethyas.com/guides/deploy/vercel/)) and import your Git repository as a new site/project. <br>
  <br>Many common hosts will recognize your project as a Hyas site, and should choose the appropriate configuration settings to 
  build and deploy your site as shown below. (If not, these settings can be changed.)
  
  {{< callout context="note" title="Deploy Settings" icon="info-circle" >}}
  
  - **Build Command:** `hyas build` or `npm run build`
  - **Publish directory:** `public`

  {{< /callout >}}

3. Click “Deploy” and your new website will be created at a unique URL for that host (e.g. `new-hyas-site.netlify.app`).

<br>The host will be automatically configured to watch your Git provider’s main branch for changes, and to rebuild and republish your site at each new commit. These settings can typically be configured in your host provider’s dashboard UI.

### CLI Deployment {#section-2.2}

Some hosts will have their own command line interface (CLI) you can install globally to your machine using npm. Often, using a CLI to deploy looks something like the following:

1. Install your host’s CLI globally, for example:
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

2. Run the CLI and follow any instructions for authorization, setup etc.

3. Build your site and deploy to your host<br>
  <br>Many common hosts will build and deploy your site for you. They will usually recognize your project as a Hyas site, and should choose the appropriate configuration settings to build and deploy as shown below. (If not, these settings can be changed.)<br>
  {{< callout context="note" title="Deploy Settings" icon="info-circle" >}}
  - **Build Command:** `hyas build` or `npm run build`
  - **Publish directory:** `public`

  {{< /callout >}}
  Other hosts will require you to [build your site locally](#section-3) and deploy using the command line.

<br>

## Building Your Site Locally {#section-3}
Many hosts like Netlify and Vercel will build your site for you and then publish that build output to the web. But, some sites will require you to build locally and then run a deploy command or upload your build output.

You may also wish to build locally to [preview your site](#section-4), or to catch any potential errors and warnings in your own environment.

Run the command `npm run build` to build your Hyas site.

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

By default, the build output will be placed at `public/`. This location can be changed using the [`publishDir` configuration option](https://gohugo.io/getting-started/configuration/#publishdir).

## Previewing Your Site Locally {#section-4}
Next to Hugo’s built-in development server, Hyas ships with [http-server](https://github.com/http-party/http-server), a simple, zero-configuration command-line static HTTP server.

Run the command `npm run preview` to preview your Hyas site.

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

The `http-server` script is configured to run with [gzip](https://developer.mozilla.org/en-US/docs/Glossary/GZip_compression), [brotli](https://developer.mozilla.org/en-US/docs/Glossary/Brotli_compression), and [CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS) enabled. These settings can be changed using the [available options](https://github.com/http-party/http-server#available-options).


<br>

---

<br>

{{< callout context="note" title="How this page was done" icon="info-circle" >}}
  
  This Callout exist for the purpose of explaining how this page was made, as requested for the TECAA course.

  #### Document Sections
  As can be seen on the Table of Contents available on the left side of the page, this document is divided into various sections. This can be achieved in our Doks Theme by making use of markdown headers, by adding `#` before the text I want to make as a Header. The more `#` added before a text define their type. For example, `# Header1` defines a h1 Header, `## Header2` defines a h2 header, and so on. On this page was done the following:

  ```markdown
    ## Deployment Guides {#section-1}
    ## Quick Deploy Options {#section-2}
    ### Website UI {#section-2.1}
    ### CLI Deployment {#section-2.2}
    ## Building Your Site Locally {#section-3}
    ## Previewing Your Site Locally {#section-4}
  ```

  For each section was also defined a `{section-x}`. This was implemented in order to be able to reference these sections on hyperlinks, to be explored further.

  #### Thematic Breaks (Horizontal Lines)
  To create a horizontal line in order to divide the page's content or even Header from the text, as can be seen right after the page's main Title, one can use three or more consecutive hyphens, underscores or asterisks. For this page `---` (triple hyphens) was used to create the thematic breaks, like the following one:
  
  --- 

  #### Bold Text
  For the text that can be seen in bold, in the middle of phrases, this could be achieved by placing ** before and after the text desired to be in bold. For example, **this** is in bold by doing `**this**`.

  #### Link Cards
  To create the [Development Guides section](#section-1) Link-Cards and Card-Grids were used. This is the feature our team presented in the Hands-On for TECAA.
  Each row of Cards was created by using Card-Grids, and each column of that row using a Link-Card, as can be seen in here:

  {{< figure
  src="images/linkcards.png"
  alt=""
  caption="">}}

  #### Hyperlinks
  Every hyperlink found within this page was done by using whats default for markdown files, `[Link Text](URL)`.
  Here, hyperlinks where used in too different ways:
  1. To redirect to another page or website, for example for the Hyas Documentation, the following was done:<br> `[Netlify](https://docs.gethyas.com/guides/deploy/netlify/)`

  2. To redirect to a section inside this page the added text to the titles, `{section-x}`, was used:<br> `[preview your site](#section-4)`

  #### Lists
  This page presents two different types of lists, ordered ones and unordered ones.
  To create the ordered lists, present in many of the sections of this page, the following was done:

  ```markdown
    1. Item 1
    2. Item 2
    3. Item 3

  ```

  To create the unordered lists, instead of using numbers followed by a dot a hyphen was used, just like what happens in markdown files:

  ```markdown
    - Item 1
    - Item 2
    - Item 3
  
  ```

  #### Callouts
  The use of Callouts were and idea brought about from a Hands-On presented by another TECAA team. While Callouts are not created in the same way in this Doks themed site, they do the same and look similar.
  To create the Callouts used in this page, including the one used for this section, the following was done:

  {{< figure
  src="images/callout.png"
  alt=""
  caption="">}}

  By changing the attributes we can create other types of callouts, changing its colour, title and even associated icon, as can be seen in the examples below: 

  {{< figure
  src="images/callout_examples.png"
  alt=""
  caption="">}}

  #### Inline Code Formatting
  Along this page there can be seen two different types of formatting for highlithing commands and bash code.<br>
  For small pieces of code or commands that I want to display in the middle of a phrase, I used ´ between the text to format. 
  For example, to get `npm run preview`, I did the following with backticks:

  ```markdown
    ´npm run preview´
  ```

  For larger pieces of code or commands, and to create a larger box as can be seen in the example above, there are two different styles that can be implemented. 
  To make a box similar to a bash command line, I did the following using triple backticks:
  
  ```markdown
    ```bash
      Text Here
    ```
  ```

  This results in:
  ```bash
    Text Here
  ```

  To create a box that resembles and works like a markdown file, like the one I'm using here, I substituted the "bash" option in the formula with "markdown":

  ```markdown
    ```markdown
      Text Here
    ```
  ```

  Resulting in:

  ```markdown
    Text Here
  ```

  #### Tabs
  Tabs were used along the page to showcase the same commands for different terminals (command lines).
  To create the tabs, I used the "tabs" and "tab" shortcodes, as can be seen in the following example:

  {{< figure
  src="images/tabs.png"
  alt=""
  caption="">}}  

  #### Images
  The images used along the page, and in the rest of the website as matter of fact, are stored in the assets folder of our project:

  {{< figure
  src="images/assets.png"
  alt=""
  caption="">}}

  The file `module.toml` keeps track of the assets folder:

  {{< figure
  src="images/moduletoml.png"
  alt=""
  caption="">}}

  Images were used in this page only in the current section to showcase code lines. The images were implemented like can be seen here:

  {{< figure
  src="images/imageexample.png"
  alt=""
  caption="">}}

{{< /callout >}}

<br>

---