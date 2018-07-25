---
title: "Buttons"
---

### Introduction

Allowing people to add buttons to their content is a much requested feature. Although HTML is allowed in Markdown, most people do not know how to write HTML. Others cannot remember the way button classes should be added in Markdown or they use a WYSIWYG editor that does not allow them to do so. This script simplifies the process of adding buttons to Markdown content.

### How it works

The script looks for a link where the link text is cotained by square brackets, like this: `[link text]`. It will remove the brackets and add `.btn` and `.btn-primary` classes to the link. If you use Twitter Bootstrap, these buttons will be automagically styled. If not, you will have to add these classes to your CSS.

[expand]

```
{% include buttons.html %}
```

Note that the page works perfectly fine when this script does not run. The link just has some brackets around it.

[/expand]

### Installation

Step 1. Download the file [buttons.html](https://raw.githubusercontent.com/xtapo/jekyllcodex/gh-pages/_includes/buttons.html)
<br />Step 2. Save the file in the '_includes' directory of your project
<br />Step 3. Make sure the bottom of your layout document looks like this:

```
{% raw %}...
<script src="/js/jquery.min.js"></script>
{% include buttons.html %}
</body>
</html>{% endraw %}
```