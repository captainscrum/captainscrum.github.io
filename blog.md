---
layout: main
title: "Le blog"
---

<div class="posts row" itemscope itemtype="http://schema.org/Blog">
    
    {% for post in site.posts %}
    
    <div class="col-xs-12 col-sm-4 center-xs pa" itemscope itemtype="http://schema.org/BlogPosting" class="post-title">
        <a href="{{ post.url }}" class="link">
            <img src="{{ post.image }}" style="max-width: 100%" />
            <h4 itemprop="headline" itemprop="name">{{ post.title }}</h4>
            <small>
                <time datetime="{{ post.date | date_to_xmlschema }}" class="hide-on-mobile">
                    <meta itemprop="datePublished" content="{{ post.date | date_to_xmlschema }}" />
                    {% assign m = post.date | date: "%-m" %}
                    {{ post.date | date: "%-d" }}
                    {% case m %}
                        {% when '1' %}Janvier
                        {% when '2' %}Février
                        {% when '3' %}Mars
                        {% when '4' %}Avril
                        {% when '5' %}Mai
                        {% when '6' %}Juin
                        {% when '7' %}Juillet
                        {% when '8' %}Août
                        {% when '9' %}Septembre
                        {% when '10' %}Octobre
                        {% when '11' %}Novembre
                        {% when '12' %}Décembre
                    {% endcase %}
                    {{ post.date | date: "%Y" }}
                </time>
            </small>
        </a>
    </div>
    {% endfor %}
</div>
