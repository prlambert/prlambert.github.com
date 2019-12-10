---
layout: page
title: Bookshelf
permalink: /bookshelf/
current_about: false
---

# Bookshelf
*This was inspired by Patrick Collison's [bookshelf](https://patrickcollison.com/bookshelf) and Nassim Taleb's [description of Umberto Eco's library](https://books.google.com/books?id=GSBcQVd3MqYC&newbks=1&newbks_redir=0&lpg=PP1&dq=the%20black%20swan&pg=PA1#v=onepage&q&f=false) at the beginning of The Black Swan.*


This page lists most of the books on my physical bookshelf. I've moved a couple times as an adult and done a few purges, so these bias towards my recent interests. 

Sonia (my wife) says I have a book buying addiction. I don't want this page to give the impression this is an exercise in ego, so I need admit this up front: I've only read 25% of these books. That might be generous. I've read a few chapters of another 10-15%, or use them reference texts. Over half I've never opened. I consider those my reading list, and I always seem to add to it faster than I can read.

I'm organizing my books by broad area because some level of organization probably helps you when reading this. It's also roughly how I aspire to organize my physical bookshelf, which is usually in a semi-disordered approximation of these lists. Some of the books could live in multiple categories. The categories aren't standard, they're my labels. 

I've included a Top 10 section to call out a few books that had an outsized impact on my thinking. I've read all of those. The 10 aren't ordered and each book is also listed in a category section.

{% assign sections = site.data.booksections %}

<div id="sectionlinks"> 
{% for category in site.data.books  %}
{% assign section = sections[category.section] %}
	<a href="#{{section.link}}">{{section.title}}</a> | 
{% endfor %}
</div>

{% for category in site.data.books  %}

{% assign section = sections[category.section] %}

<h3 id="{{section.link}}">{{section.title}}</h3>

| Title |   Author   |
| ----------- | ----------- |
{% for book in category.books %}| [{{ book.title }}]({{book.link}}) | {{ book.author }} |
{% endfor %}

{% endfor %}
