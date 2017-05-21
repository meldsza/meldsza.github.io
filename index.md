
{% for post in site.posts %}

##    {{post.title}}
    <div class="content">
        {{ post.content }}
    </div>

{% endfor %}
