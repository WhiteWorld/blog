---
layout: post
title: "Rails4 Cheat Sheet"
description: ""
category: rails
tags: [ruby,cheatsheet]
---
{% include JB/setup %}

## ActiveRecord
- 映射关系

{% highlight ruby linenos=table %}
has_many
belongs_to
{% endhighlight%}

- 属性设置

{% highlight ruby linenos=table %}
validates_presence_of
validates_uniqueness_of
{% endhighlight%}


## 中文化

{% highlight ruby linenos=table %}
config.i18n.load_path += Dir[Rails.root.join('my', 'locales', '*.{rb,yml}').to_s]
config.i18n.default_locale = :'zh-CN'
# then,add files in config/locales
{% endhighlight%}

## Views

{% highlight ruby linenos=table %}
config.i18n.load_path += Dir[Rails.root.join('my', 'locales', '*.{rb,yml}').to_s]
#link_to
<%= link_to user_path(@user) do%>
<%= link_to game_dislike_path(@game), class:'btn btn-sm btn-info' do%>已收藏 <% end %>
#form add class
html: {method: :put, class: 'form-horizontal'}
{% endhighlight%}
