---
title: "Customization"
description: "List of some customization perks Doks has to offer."
summary: ""
date: 2024-04-22T13:08:37+01:00
lastmod: 2024-04-22T13:08:37+01:00
draft: false
weight: 999
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

This page is dedicated to show you the customization power of Doks. All of the features down below were used in the development of this website. You can also visit the Doks Documentation for more information and available features we didn't get to use.

Since Doks is a theme still in development, demonstration resources are not common and very easy to find.

## Doks's System
Costumization in doks is made through the `assets/scss` files available once you build the initial doks project:
- `_variables.scss`: As the name implies, this file is to be used for variable declarations for later use and to avoid repetition of styles in the main costumization file. Doks already brings with it some custom variables like <b>$primary</b>, but gives you the freedom of creating your own variables.
- `_custom.scss`: This is the main file for your custom styles. You can choose to write CSS or SCSS. Furthermore, it also has access to the variables created on the variables files. If you wish, you can also create other SCSS files, which with their own purpose, and connect to this file.

{{<callout context="note" icon="info-circle">}} Doks let's you override every variable already predefined. {{</callout>}}

## Fonts
Doks enables you to customize the type of font and weight/size associated to the different elements present in the pages.
Its makes use of two methods for font definition:
- System fonts
- Google fonts

### System fonts
The use of system fonts ensures faster loading of the documentation because i does not require extra time and bandwith to dowload font files

If you want to add system fonts to your project, add those in the `assets/scss/common/_variables-custom.scss`:
```scss
// you can choose which fonts are recognizable
$font-family-sans-serif:  "Noto Sans", "Liberation Sans", Arial, sans-serif;
```

### Google fonts
In alternative to using system fonts, you can also make use of Google Fonts. The recommended usage is to self-host the fonts with a tool like google-webfonts-helper or Fontsource.

Normally speaking, Google fonts can offer a wider range of options for each font available. You can set initial font-weight, font type (serif or not), type of chartset and more. Google fonts offers you more control right of the bat compared to system fonts that are limited to what is installed and loaded already.

For example let's try and use the "Montserrat" font:
1. Visit google-webfonts-helper, and select Montserrat. You have a good amount of options to choose. We'll go with "lating, "regular" and "500".
2. Copy CSS (using only the prefix /fonts/montserrat) as past on `assets/scss/common/_custom.scss`:
```scss
// don't forget to change the font weight to your preference.
/* montserrat500-regular - latin */
@font-face {
  font-display: swap; /* Check https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-display for other options. */
  font-family: 'Montserrat';
  font-style: normal;
  font-weight: 500;
  src: url('../fonts/montserrat-v26-latin-regular.woff2') format('woff2'); /* Chrome 36+, Opera 23+, Firefox 39+, Safari 12+, iOS 10+ */
}
```
3. Download files, extract and paste fonts in `static/fonts/montserrat/`
4. Add to `assets/scss/common/_variable-custom.scss`
```scss
// you can choose which fonts are recognizable
$font-family-sans-serif:  "Montserrat", "Noto Sans", "Liberation Sans", Arial, sans-serif;
```
5. Preload the fonts to avoid Cumulative Layout Shift: copy to `node_modules/@hyas/doks-core/layouts/partials/head/resource-hints.html` to `layouts/partials/head/resource-hints.html` and add the font:
```html
<link rel="preload" href="{{ "fonts/montserrat/montserrat-v26-latin-regular.woff2" | absURL }}" as="font" type="font/woff2" crossorigin>
<link rel="preload" href="{{ "fonts/montserrat/montserrat-v26-latin-500.woff2" | absURL }}" as="font" type="font/woff2" crossorigin>
```

### Font size
Doks has a good amount of custom variables for you to use, but it still hands you de power of custom styles, that could be written in SCSS or CSS. We can use the powers of Doks to make our job easier to maintain a consistent design theme to our pages

As talked before, you can define variables for font size in the `_variables-custom.scss`, or just write your styles directly into `_custom.scss`.

A simple example would be:
```scss
// set a base font size
:root {
  --base-font-size: 1.5rem;
}
```
```scss
// h1 size according to the predefined variable
h1 {
  font-size: calc(var(--base-font-size) + 1.5vw);
}

// h2 size is defined directly in the file
h2 {
  font-size: 2rem;
}
```

Fonts normally come with specific weight values as [Google font](#google-fonts) recalls. Still, doks lets you change the font weight with simple CSS:
```scss
// change roots font weight
:root {
  font-weight: 700; // change to the desired weight
}
```

## Color Theme
Editing the colors around the doks theme ends up following the same principal of creating your own CSS or SCSS styles and dump them into the `_custom.scss` file.

Similarly to the font customization, you can set predefined variables that help you maintain a cosistent look to your website. The Doks theme already comes with predefined variables you can also make use alongside your own variables:

```scss
// change the hover color of links
a:hover {
  color: #b5dec8;
}
```

You are given completely freedom of what to change. We incentivize you to experiment further and create your own color themes.

{{<callout context="tip" title="Check your HTML">}}
Check your generated HTML file when you wish to change a very specific part of the doks document. Along with the material you write, the HTML also contains the classes it uses for the styling.
{{</callout>}}

## Shortcodes
Doks supports the use of shortcodes in the page's markdowns.

Shortcodes are a neat way of incorporating HTML with your Markdowns. To use a shortcode you need to encapsulate the html between `{{}}`.

Shortcodes can offer a variety of functionalities, though doks mostly uses them as navigation links.

There are a many types of specific shorcodes, which we will cover in this guide.

{{<callout context="note">}}
You can follow a more in depth guide of shortcodes at [Doks: Shortcodes](https://getdoks.org/docs/basics/shortcodes/)
{{</callout>}}

### Callouts
Callouts are used to give additional information, like notes or warnings the user should take into consideration.

Callouts can be creates with a `title`, `context` and `icon` associations. Callout contexts fall into four different and straightforward types: `note`, `tip`, `warning` and `caution`.

{{<callout context="note" title="Note" icon="info-circle">}}
Used for additional notes.
{{</callout>}}
{{<callout context="tip" title="Tip" icon="rocket">}}
Used for extra interesting tips you might want to give
{{</callout>}}
{{<callout context="caution" title="Caution" icon="alert-triangle">}}
Alert the user about a possible bug or roadblock.
{{</callout>}}
{{<callout context="danger" title="Danger" icon="alert-octagon">}}
Alert the user to possible problem.
{{</callout>}}

The basic syntax for these elements are as follows:
```html
<callout context title icon></callout>
```

As reinforced earlier, you can customize these callouts as much as you want but it isn't advised to do so, has they serve a very specific purpose.

### Details
The details element works as a container button, that once clicked hides or shows additional information, that can be personlized for different purposes. I can function similarly to notes, or it can function as a navigation link hub that links every header in the page. You are free to create your own "sub-markdown" inside it.

The basic syntax of a details box is `<details "Title"></details>`.

By default, details boxes initialize in a closed state. You can change that property with the `open` flag.

An example of the a details element would be:

{{<details "Details example" >}}
Choose the message you want to convey...

Create code boxes if you wish to...
```html
<div></div>
```

Or navigate through the website with links.

[Go back to the top](#top)
{{</details>}}


### Tabs
Tabs are a good way of organizing your information when you have multiple forms of doing things. A perfect use for this element you'll be instalation processes. Since often installing software depends on the OS, you can create a Tabs elements with tabs for each OS you need.

Again, doks gives you complete freedom to use these elements in which way you seem fit.

To use Tabs you should create a `tabs` element followed by the number of `tab` elements you want. You can associate a title for both the `tabs` element as well as the `tab` elements. The creation of a tab should be done as follows:

```html
<!--Don't forget to encapsulate these HTML elements in {{ }} to use them in markdown-->
<tabs "Tabs Body Title">
  <!--You can create as many tab elements as you wish-->
  <tab "Tab Title">
    Content of the tab
  </tab>
</tabs>
```

An example of a Tabs element would be:
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
Link cards offers you a slick designed box with the function of a navigation link for both inside and outside links.

The Syntax to use these links are defined as `<link-card title description href target>`. Link cards require a `title` and a `href` attribute to be defined. Optionally, you can also set a `description` or other link attributes such as `target`.

{{<link-card
  title="Link Card example"
  description="Let's go back to the top of the page with this"
  href=#top
>}}

```html
<!--You can redirect the user to a website, another page or another header in the same page through the href-->
<!--You can also have target="_blank" if you want to open a new tab when the link card is clicked-->
<link-card title="Link Card example" description="Let's go back to the top of the page with this" href=#top>
```

### Card Grids
As the name entices, card grids help you organize your link cards following an horizontal grid layout.

The syntax used is `<card-grid></card-grid>`, where card-grid can contain multiple link card elements, similar to what we saw at [tabs](#tabs).

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

### How this page was made
The page makes use of the different topics already talked about.

It makes abundant abuse of code blocks, to make the documentation more pratical and more interactive with the user.

It also follows the website's universal design guidelines, defined by the colors used, structure and sizes / weights.

Finally is makes use of callouts to work primarily as notes for the user to take into account.

Apart from that, all the others elements were used for teaching purposes.

