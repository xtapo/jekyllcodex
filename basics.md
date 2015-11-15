---
title: Features
layout: page
permalink: /basics/
---

## Layout

### Different templates

If you need different templates, for posts and pages for example, you can create them in the directory '_layouts'. Your template is alsmost the same as your 'index.html' file, you created in the 'Getting started'. The only difference is that you should name it something like 'post.html', 'page.html' or 'default.html' and replace the content with: 

<pre>&lcub;&lcub; content &rcub;&rcub;</pre>

Furthermore you have to add three extra lines at the top of your 'index.html' file.

<pre>---<br />layout: page<br />---</pre>

### Using Sass

Jekyll supports Sass out of the box. This means you can use 'style.scss' anywhere in your project and refer to it as 'style.css'. You will have no excuse for using CSS anymore. Want to compress the outputted CSS? Just add the following two lines to your '_config.yml' file.

<pre>sass:<br />&nbsp;&nbsp;style: compressed</pre>

## Blogging

### Setup

Go to your 'Collections' in CloudCannon and see if you already have support for posts. If not, create a '_posts' directory in the root of your project and look again. Blogs have a default URL like this: YYYY/MM/DD/title-of-the-blog.html. Listing your blog items requires the following Liquid code:

<pre>&lt;h3&gt;Posts&lt;/h3&gt;
&lt;ul&gt;
  &lcub;% for post in site.posts %&rcub;
  &lt;li&gt;
    &lt;a href="&lcub;&lcub; post.url &rcub;&rcub;">&lcub;&lcub; post.title &rcub;&rcub;&lt;/a&gt;
  &lt;/li&gt;
  &lcub;% endfor %&rcub;
&lt;/ul&gt;</pre>

### Custom permalinks

To change the permalinks of your blog articles, simply add this single line to your '_config.yml':

<pre>permalink: /blog/:year/:month/:day/:title/</pre>


## SEO

### Pretty URL's

When you want your URL's to be pretty, simply use the 'old-school' approach. Create an 'index.html' in the root for the homepage and a folder called 'about' with another 'index.html' file inside for your 'about' page... and so on. You will take advantage of this on a later moment when you need to build a menu, based on the page hierarchy.

### Description tag
### Canonical link
### Sitemap XML
### Atom feed

## Menu's

### Set active class

Setting the active class on a li that is used for navigation goes like this:

<pre>&lt;li &lcub;% if '/getting-started/' == page.url %&rcub;&gt; ... &lt;/li&gt;</pre>

If you want this to work for 'getting-started/' and 'getting-started/index.html' you have to use this:

<pre>&lt;li &lcub;% if '/getting-started/' == page.url|remove:'index.html' %&rcub;&gt; ... &lt;/li&gt;</pre>

### Dynamic menu

Creating a menu that automagically discovers and adds new pages is also possible with plain Liquid. More info and a demo can be found on [GitHub](https://github.com/jnvsor/jekyll-dynamic-menu). When you put the two files ('menulevel' and 'menushow') in your '_includes' folder you can generate a dynamic menu with the following command:

<pre>&lcub;% include menulevel url='' %&rcub;</pre>

## Need more?

Look at the add-ons for more solutions. 