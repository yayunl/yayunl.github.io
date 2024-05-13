---
layout: post
title:  "hello jekyll!"
date:   2015-02-10 15:14:54
categories: jekyll
tags: jekyll
excerpt: 当年创建 jekyll 时默认的一篇文章，没什么意义，我也一直没删除，留个纪念吧。
mathjax: true
---

You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.

To add new posts, simply add a file in the `_posts` directory that follows the convention `YYYY-MM-DD-name-of-post.ext` and includes the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:

```ruby
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
```
# Introduction

Design patterns are shared among programmers and continue to be improved over time, thanks to the *Gang of Four* book [**Design Patterns: Elements of Reusable Object-Oriented**](https://www.amazon.com/Design-Patterns-Elements-Reusable-Object-Oriented/dp/0201633612) by Erich Gamma, Richard Helm, Ralph Johnson, and John Vlissides. 

Design patterns help narrow down the most effective ways of building a given application and offer examples of the same design pattern to improve your application. 

There are 23 design patterns, split into three categories: *creational*, *structural*, and *behavioral*, used in OOP, which are highly useful guidelines in software engineering.

# Factory design pattern

This section discusses the **factory design pattern**, which simplifies object creation by hiding its instantiation from clients. 

Factory design reduces complexity by separating object creation from object use and come in two forms, namely, *factory method* and *abstract factory*. The factory method returns a different object per input parameter while the abstract factory is a group of factory methods that create a related family of objects. The following section will cover the factory method theory.

# Factory Method

The factory method is based on a single function that's written to handle our object creation task. We execute it, passing a parameter that provides information about what we want. As a result, the object we wanted is created.

> An example of the factory method pattern that's used in real life is in the context of a plastic toy construction kit. The molding material that's used to construct plastic toys is the same, but different toys (different figures or shapes) can be produced using the right plastic molds. This is like having a factory method in which the input is the name of the toy that we want (for example, duck or car) and the output (after the molding) is the plastic toy that was requested.

# Abstract factory
The abstract factory design pattern is a generalization of the factory method. An abstract factory is a (logical) group of factory methods, where each factory method is responsible for generating a different kind of object. In this section, we are going to discuss some examples, use cases, and a possible implementation of this pattern.

> The abstract factory is used in car manufacturing. The same machinery is used for stamping the parts (doors, panels, hoods, fenders, and mirrors) of different car models. The model that is assembled by the machinery is configurable and easy to change at any time.


## Participants
The Abstract Factory pattern consists of the following components:

### Abstract Factory: 
- `declares` an interface for operations that create abstract product objects.

### Concrete Factory: 
- `implements` the operations to create concrete product objects.   
- each concrete factory is responsible for creating a family of related objects

### Abstract Product: 
- `declares` the common interface for the products created by the Abstract Factory.

### Concrete Product: 
- defines a product objects to be created by the corresponding concrete factory.
- `implements` the Abstract Product interfaces.

### Client:
- uses only interfaces declared by Abstract Factory and Abstract Product classes.

## Structure

The below picture illustrates the relationships among the components.
![Factory-pattern](/assets/images/factory-pattern-structure.png)

# Factory Pattern Example

In the example below, the **Abstract Products** are `Chair` and `Table`, with their corresponding **Concrete Product** implementations (`VictorianChair`, `VictorianTable`, `ModernChair`, `ModernTable`). The **Abstract Factory** is represented by the FurnitureFactory interface, which declares methods for creating `Chair` and `Table` objects. The **Concrete Factories** 
(`VictorianFurnitureFactory`, `ModernFurnitureFactory`) implement the **Abstract Factory** and provide the specific implementations of creating related objects.

The client code uses the `create_furniture` function, which takes a factory as an argument and creates a `Chair` and `Table` using that factory. 

Check out the [Jekyll docs][jekyll] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll’s dedicated Help repository][jekyll-help].

[jekyll]:      http://jekyllrb.com
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-help]: https://github.com/jekyll/jekyll-help

Block Mathjax 

$$
f(x) = ax + b
$$

Inline Mathjax $a \neq b$
**