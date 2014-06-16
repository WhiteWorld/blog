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

```ruby
  has_many
  belongs_to  
```

- 属性设置

```ruby
  validates_presence_of
  validates_uniqueness_of
```


## 中文化

```ruby
  config.i18n.load_path += Dir[Rails.root.join('my', 'locales', '*.{rb,yml}').to_s]
  config.i18n.default_locale = :'zh-CN
  # then,add files in config/locales
```

## Views

```ruby
  #link_to
  <%= link_to user_path(@user) do%>
  <%= link_to game_dislike_path(@game), class:'btn btn-sm btn-info' do%>已收藏 <% end %>
  #form add class
  html: {method: :put, class: 'form-horizontal'}
```
