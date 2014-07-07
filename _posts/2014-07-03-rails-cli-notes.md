---
layout: post
title: "Ruby on Rails 命令行笔记"
description: ""
category: Rails
tags: [CLI, Ruby, Notes]
---
{% include JB/setup %}

## 目录

* Content.
{:toc}

------

## Create Migration

创建单独的Migration

{% highlight bash %}
# 添加列
rails generate migration AddPartNumberToProducts
rails generate migration AddPartNumberToProducts part_number:string
rails generate migration AddPartNumberToProducts part_number:string:index
# 删除列
rails generate migration RemovePartNumberFromProducts part_number:string
rails generate migration AddDetailsToProducts part_number:string price:decimal
# 创建表
rails generate migration CreateProducts name:string part_number:string
# 添加reference
rails generate migration AddUserRefToProducts user:references
# 创建JoinTable
rails g migration CreateJoinTableCustomerProduct customer product
{% endhighlight%}

创建Model

{% highlight bash%}
# 创建Model
rails generate model Product name:string description:text
{% endhighlight%}

## Writing a Migration

{% highlight ruby %}
# Creating a Table
create_table :products do |t|
  t.string :name
end
# Creating a Join Table
create_join_table :products, :categories
# Changing Tables
change_table :products do |t|
  t.remove :description, :name
  t.string :part_number
  t.index :part_number
  t.rename :upccode, :upc_code
end
{% endhighlight%}

## Running Migrations

{% highlight bash%}
rake db:migrate 
# Rolling Back
rake db:rollback
rake db:rollback STEP=3
# Setup the Database
rake db:setup
# Resetting the Database
rake db:reset 
rake db:drop db:setup
{% endhighlight%}
