---
layout: default
title: 图片
---
<!-- 按tag分：清水、涩图 -->
{% assign tags = site.tags %}

<div class="well article">
{% for tag in tags %}
    {% if tag[0] == "图片" %}
        <a id="清水" style="position: relative; top: -50px"></a>
        <h2>清水</h2>
        {% assign pages_list = tag[1] %}
        {% for page in pages_list %}
            {% assign images = page.content | split: "<img src=" %}
            {% for image in images %}
                {% assign img = image | split: ' alt="" />' | first %}
                {% if img contains site.baseurl %}
                    <a href="{{ site.baseurl }}{{ page.url }}"><img src={{ img }} style="height: 200px; width: auto; object-fit: scale-down; margin-bottom: 5px;"></a>
                {% endif %}
            {% endfor %}
        {% endfor %}
        {% assign pages_list = nil %}
</div>
    {% elsif tag[0] == "涩图" %}
<div class="well article">
        <a id="涩图" style="position: relative; top: -50px"></a>
        <h2>涩图</h2>
        {% assign pages_list = tag[1] %}
        {% for page in pages_list %}
            {% assign images = page.content | split: "<img src=" %}
            {% for image in images %}
                {% assign img = image | split: ' alt="" />' | first %}
                {% if img contains site.baseurl %}
                    <a href="{{ site.baseurl }}{{ page.url }}"><img src={{ img }} style="height: 200px; width: auto; object-fit: scale-down; margin-bottom: 5px;"></a>
                {% endif %}
            {% endfor %}
        {% endfor %}
        {% assign pages_list = nil %}        
    {% endif %}
{% endfor %}
</div>

<!-- 按category分：浪浪钉、亚梅 -->
{% assign categories = site.categories %}
<div class="well article">
{% for category in categories %}
    {% if category[0] == "梅林传奇" %}
        <a id="梅林传奇" style="position: relative; top: -50px"></a>
        <h2>梅林传奇（所有图）</h2>
        {% assign pages_list = category[1] %}
        {% for page in pages_list %}
            {% unless page.tags == null %}
            {% if page.tags contains "图片" or page.tags contains "涩图" %}
                {% assign images = page.content | split: "<img src=" %}
                {% for image in images %}
                    {% assign img = image | split: ' alt="" />' | first %}
                    {% if img contains site.baseurl %}
                        <a href="{{ site.baseurl }}{{ page.url }}"><img src={{ img }} style="height: 200px; width: auto; object-fit: scale-down; margin-bottom: 5px;"></a>
                    {% endif %}
                {% endfor %}                
            {% endif %}
            {% endunless %}
        {% endfor %}
        {% assign pages_list = nil %}
</div>
    {% elsif category[0] == "浪浪钉" %}
<div class="well article">
        <a id="浪浪钉" style="position: relative; top: -50px"></a>
        <h2>浪浪钉（所有图）</h2>
        {% assign pages_list = category[1] %}
        {% for page in pages_list %}
            {% unless page.tags == null %}
            {% if page.tags contains "图片" or page.tags contains "涩图" %}
                {% assign images = page.content | split: "<img src=" %}
                {% for image in images %}
                    {% assign img = image | split: ' alt="" />' | first %}
                    {% if img contains site.baseurl %}
                        <a href="{{ site.baseurl }}{{ page.url }}"><img src={{ img }} style="height: 200px; width: auto; object-fit: scale-down; margin-bottom: 5px;"></a>
                    {% endif %}
                {% endfor %}                
            {% endif %}
            {% endunless %}
        {% endfor %}
        {% assign pages_list = nil %}
    {% endif %}
{% endfor %}
</div>