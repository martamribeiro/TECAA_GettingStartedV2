---
title: "Getting Started"
description: "Getting Started page to guide reader on the first steps to create their first website with Hugo, using the Doks theme."
summary: ""
date: 2024-04-23T15:51:55+01:00
lastmod: 2024-04-22T15:51:55+01:00
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

In this page you will learn the first steps to create your first website with **Hugo**, using the **Doks theme**.

## Install Hugo and Go

### Hugo

**Start by installing Hugo on your device.** Clicking on [this link](https://gohugo.io/installation/) you can check the installation guidelines for macOS, LINUX, Windows, BSD, and any other machine that can run the Go compiler tool chain.

After installing Hugo, you should run the following command:

| Windows | MAC |
| :----: | :----: |
| ``` choco install hugo-extended``` | ``` brew install hugo``` |

Then, check the version you are using with the following command:

```bash
hugo version
```

### Go

**Now it's time to install Go.** Clicking on [this link](https://go.dev/dl/) you can install the Go version you prefer, for your operative system.

Then, check the version you are using with the following command:

```bash
go version
```

## Create your Project

**Now, you'll need to create a new project with the Doks theme.**

### Create a new project

The recommended way to create a new Hyas + Doks project is by running the command below in your terminal, in the directory where you want to create your project:

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

This will create a new project directory with all the necessary files and configurations for your site.

### Install dependencies

```cd``` into your new project directory and install the dependencies before continuing.

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

## Visualize your project

**Now that you have your project created, it's time to visualize it.** When working locally, Hugo’s development server lets you preview your work and automatically refreshes your browser when you make changes. Inside your project directory, run the following command to start the development server:

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

This will log a message to your terminal with the URL of your local preview. Open that URL to start browsing your site.

**Congratulations, you finished the first steps to create your first website with Hugo, using the Doks theme!**

<br>

---

<br>

{{< callout context="note" icon="info-circle" >}}

  ### How this page was done
  
  This Callout exist for the purpose of explaining how this page was made, as requested for the TECAA course.

  {{< details "Headers" >}}

  Headers were strategically employed throughout the "Getting Started" page to delineate different sections and guide readers through the installation process.

  By using headers such as "Install Hugo and Go", "Create your project", and "Visualize your project", the content is logically organized, making it easier for users to navigate and understand each step involved in creating their first website with Hugo and the Doks theme.

  Headers are denoted by one or more hash symbols ```#``` followed by a space and the header text. The number of hash symbols determines the level of the header, with one hash symbol ```#``` representing the highest level (H1), two hash symbols ```##``` representing the second level (H2), and so on.

  Example:

  ```bash
  # Header 1
  ## Header 2
  ### Header 3
  ```

  {{< /details >}}

  {{< details "Tabs" >}}

  Tabs were utilized within the installation steps to provide separate instructions for different package managers. This approach ensures that readers can quickly access the instructions relevant to them without being overwhelmed by unnecessary information.

  Tabs are implemented using shortcodes. They allow users to switch between different sets of information within a single section of content.

  Example:

  {{< figure
  src="images/tabs_gs.png"
  alt="Image showing a code snipet where Tabs are implemented."
  caption="">}}

  {{< /details >}}

  {{< details "Tables" >}}

  Tables were incorporated to present installation commands for different operating systems. Tables allow for easy comparison between installation options, enabling users to choose the method that best suits their preferences and requirements.

  Tables are created using pipe symbols ```|``` to separate columns and hyphens ```-``` to define the table headers. Each row represents a separate entry in the table, with cells separated by pipe symbols.

  Example:

  ```bash
  | Windows | MAC |
  | :----: | :----: |
  | ``` choco install hugo-extended``` | ``` brew install hugo``` |
  ```

  {{< /details >}}

  {{< details "Hyperlinks" >}}

  Hyperlinks were strategically inserted throughout the page to provide easy access to external resources and relevant documentation. By including hyperlinks to the official Hugo installation page and the Go download page, users can quickly access additional information and resources to assist them in the installation process.

  Hyperlinks are created using the syntax ```[link text](URL)```, where link text represents the clickable text displayed to users and URL specifies the destination.

  Example:

  ```bash
  [this link](https://gohugo.io/installation/)
  ```

  {{< /details >}}

  {{< details "Code Blocks" >}}

  Code blocks were used to display commands. By presenting commands in a structured and formatted manner, users can easily identify and execute them. Additionally, code blocks allow for easy copy-and-paste functionality, enabling users to replicate the commands accurately and efficiently.

  Code blocks are enclosed within triple backticks (```).

  Example:

  {{< figure
  src="images/codeblock_gs.png"
  alt="Image showing a code snipet where a Code Block is implemented."
  caption="">}}

  {{< /details >}}

  {{< details "Callout" >}}

  In the end of the page, a Callout was included to explain how the page was created. This Callout  provides important information that can be useful for the users once they start working on their own pages.

  Callouts are implemented using custom shortcodes. They are used to draw attention to specific information or provide additional context.

  Example:

  {{< figure
  src="images/callout_gs.png"
  alt="Image showing a code snipet where a Callout is implemented."
  caption="">}}

  {{< /details >}}

  {{< details "Figures" >}}

  In the callout section, figures were included to visually represent examples of how different elements were implemented in the "Getting Started" page, especially the ones that could not be put inside code block, for formatting reasons.

  Example:

  {{< figure
  src="images/figures_gs.png"
  alt="Image showing a code snipet where a figure is implemented."
  caption="">}}

  {{< /details >}}

  By strategically incorporating headers, tabs, tables, hyperlinks, code blocks, callouts, and figures throughout the "Getting Started" page, the content is effectively organized, presented, and explained to users. Each element serves a specific purpose in guiding users through the installation process and providing them with the necessary information and resources to create their first website with Hugo and the Doks theme.


{{< /callout >}}

<br>

---