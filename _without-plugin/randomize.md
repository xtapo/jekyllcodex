---
title: "Randomize"
---

### Introduction

Sometimes you want to create a randomized list of items. In a static site this is quite hard, because random in Liquid means random at build time. This script, however, randomizes at each visit/page load using Javascript.

### How it works

This scripts shuffles all items in the page that have the class randomize. Make sure you hide the items you do not want to show with CSS. To prevent the potentially massive amount of DOM elements to take up too much memory and bandwith, you can write all image sources as 'data-src'. This script will rewrite only the visible ones to 'src'. The same can be done for background images, by using 'data-style' on your elements.

[expand]

Here is some example HTML:

```
<ul>
  <li class="randomize">Item 0</li>
  <li class="randomize">Item 1</li>
  <li class="randomize">Item 2</li>
  <li class="randomize">Item 3</li>
  <li class="randomize">Item 4</li>
  <li class="randomize">Item 5</li>
  <li class="randomize">Item 6</li>
  <li class="randomize">Item 7</li>
  <li class="randomize">Item 8</li>
  <li class="randomize">Item 9</li>
</ul>
```

And some example CSS:

```
.randomize {display: none;}
.randomize:nth-child(1), .randomize:nth-child(2), .randomize:nth-child(3) {display: block;}
```

Note that this script can be used only once on a page.

[/expand]

### Installation

Step 1. Download the file [randomize.html](https://raw.githubusercontent.com/xtapo/jekyllcodex/gh-pages/_includes/randomize.html)
<br />Step 2. Save the file in the '_includes' directory of your project
<br />Step 3. Make sure the bottom of your layout document looks like this:

```
{% raw %}...
<script src="/js/jquery.min.js"></script>
{% include randomize.html %}
</body>
</html>{% endraw %}
```