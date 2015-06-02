---
layout: post
title: "How to render all flash messages in Twig and Bootstrap 3"
date: 2015-06-01 13:52:49 +0300
comments: true
categories: [symfony2, twig, bootstrap3]
---

Here is how to do it:
{% highlight html %}
{% raw %}
{% if app.session.started %}
    {% for type, flashes in app.session.flashbag.all %}
        {% for message in flashes %}
            <div class="alert alert-{{ type }} alert-dismissible" role="alert">
                <button type="button" class="close" data-dismiss="alert">
                    <span aria-hidden="true">&times;</span><span class="sr-only">Close</span>
                </button>
                {{ message }}
            </div>
        {% endfor %}
    {% endfor %}
{% endif %}
{% endraw %}
{% endhighlight %}