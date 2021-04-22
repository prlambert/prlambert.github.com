---
layout: page
title: Bookshelf
permalink: /bookshelf/
current_about: false
---

# Bookshelf
*Last updated: January 2020*

*This was inspired by Patrick Collison's [bookshelf](https://patrickcollison.com/bookshelf) and Nassim Taleb's [description of Umberto Eco's library](https://books.google.com/books?id=GSBcQVd3MqYC&newbks=1&newbks_redir=0&lpg=PP1&dq=the%20black%20swan&pg=PA1#v=onepage&q&f=false) at the beginning of The Black Swan.*

I don't want this page to give an inflated impression so I need to admit this up front: I've only read a quarter these books. Maybe. That is probably generous.

This page contains most of the books on my physical bookshelf, my kindle, and my Amazon wishlist. I've moved a couple times as an adult and done a few purges, so many of the books I bought earlier in life aren't listed. I haven't included textbooks, children's books, travel books, cookbooks, or anything I found too embarassing.

I'm organizing my books broadly by subject because I hope it helps you navigate. It's also roughly how I aspire to organize my actual bookshelf, which is usually in a semi-disordered approximation of these lists. Some of the books could live in multiple categories. This is entirely my own categorization, i.e. non-standard.
<!-- 
I've included a section to call out a few books that had an outsized impact on me. I've read all of those. Each of those are also listed in a subject section. -->

All sections are organized alphabetically by author's first name. 

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
{% for book in category.books %}| {{ book.title }} | {{ book.author }} |
{% endfor %}

{% endfor %}
