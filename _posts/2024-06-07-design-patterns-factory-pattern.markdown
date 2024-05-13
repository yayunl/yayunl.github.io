---
layout: post
title:  "Design patterns in Python: Factory Pattern"
date:   2024-06-07 12:00:00
categories: programming
tags: design-patterns
excerpt: design-patterns-in-python
mathjax: true
---

* content
{:toc}

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

### Code example in Python:
```python
from abc import ABC, abstractmethod

# Abstract Products
class Chair(ABC):
    @abstractmethod
    def sit_on(self):
        pass

class Table(ABC):
    @abstractmethod
    def put_on(self):
        pass

# Concrete Products
class VictorianChair(Chair):
    def sit_on(self):
        print("Sitting on a Victorian Chair")

class VictorianTable(Table):
    def put_on(self):
        print("Putting something on a Victorian Table")

class ModernChair(Chair):
    def sit_on(self):
        print("Sitting on a Modern Chair")

class ModernTable(Table):
    def put_on(self):
        print("Putting something on a Modern Table")

# Abstract Factory
class FurnitureFactory(ABC):
    @abstractmethod
    def create_chair(self) -> Chair:
        pass

    @abstractmethod
    def create_table(self) -> Table:
        pass

# Concrete Factories
class VictorianFurnitureFactory(FurnitureFactory):
    def create_chair(self) -> Chair:
        return VictorianChair()

    def create_table(self) -> Table:
        return VictorianTable()

class ModernFurnitureFactory(FurnitureFactory):
    def create_chair(self) -> Chair:
        return ModernChair()

    def create_table(self) -> Table:
        return ModernTable()

# Client code
def create_furniture(factory: FurnitureFactory):
    chair = factory.create_chair()
    table = factory.create_table()
    return chair, table

# Using the factories
victorian_factory = VictorianFurnitureFactory()
modern_factory = ModernFurnitureFactory()

victorian_chair, victorian_table = create_furniture(victorian_factory)
modern_chair, modern_table = create_furniture(modern_factory)
```

### Illustration of the above code example
![Factory-pattern-illustration](/assets/images/factory-pattern-illustration.png)

