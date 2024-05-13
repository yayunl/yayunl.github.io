---
layout: post
title:  "Design patterns in Python: Builder Pattern"
date:   2023-06-07 15:00:00
categories: programming
tags: design-patterns
---
* content
{:toc}


# Introduction
The **Builder pattern** is a *creational* design pattern described in the book "Design Patterns: Elements of Reusable Object-Oriented Software" by the Gang of Four. This pattern is used to construct complex objects step by step, allowing the same construction process to create different representations of an object.

The key concept behind the **Builder pattern** is to separate the *construction* of an object from its *representation*. By doing so, the same construction process can be used to create different representations. This pattern provides a way to create an object incrementally, specifying different attributes or steps of the construction process as needed.

## Real-world examples
> In our everyday life, the builder design pattern is used in fast-food restaurants. The same procedure is always used to prepare a burger and the packaging (box and paper bag), even if there are many different kinds of burgers (classic, cheeseburger, and more) and different packages (small-sized box, medium-sized box, and so forth).    

Quoted from Chapter 16 in *Advanced Python Programming ( Second Edition)*

The difference between a classic burger and a cheeseburger is in the representation, and not in the construction procedure. In this case, the director is the cashier who gives the crew instructions about what needs to be prepared, and the builder is the person from the crew that takes care of a specific order.  

## Benefits
Here are the benefits of using the Builder pattern:
1. Flexibility of a product's internal representation. 
2. Isolation of construction and representation. 
3. Finer control over the construction process. The Director instructs the Builder to build parts of a product step by step. Only when the product is finished does the Director retrieve it from the builder.

# Participants 
There are four participants involved in the **Builder pattern**:

- **Builder**: 
  - *specifies an abstract interface* for creating parts of a `Product` object.
- **Concrete Builder**: 
  - *implements* the `Builder` interface to provide specific construction steps and configurations. 
  - *defines* and *keeps track* of the representation it creates.
  - *provides an interface* for retrieving the product.
- **Director**: 
  - *constructs an object* using the `Builder` interface.
- **Product**: 
  - *represents* the object being constructed.
- **Client**: 
  - *creates instances* of the builder and director. 
  - *uses* the director to construct different types of the product by calling the appropriate construction methods. (The builder, then, handles requests from the director and adds parts to the product.)
  - *retrieves* the product from the builder.

# Structure illustration
The following picture illustrates the relationships among the components of the **Builder pattern**.
![Builder-pattern](/assets/images/builder-pattern-structure.png)


# Code implementation (Python)

In the following code example in Python, the **Product** `Pizza` presents the pizza object being constructed. It has attributes for crust, toppings, and cheese. 


The **Builder** `PizzaBuilder` class provides the construction methods to set the attributes of a pizza, the product, step by step. It keeps track of the product being built. 


The `MargheritaBuilder` and `PepperoniBuilder` classes inherit from the `PizzaBuilder` class. Each **concrete builder** class provides its own implementation of the construction methods (`set_crust()`, `add_topping()`, `set_cheese()`), allowing customization of the construction process for Margherita and Pepperoni pizzas, respectively. The concrete builders represent different variations of the product construction, adhering to the Concrete Builder participant in the Builder pattern.


The **Director** `PizzaDirector` manages the construction process using the builder. It defines higher-level construction methods that utilize the builder's methods to construct specific configurations of the product.


The **client** code creates instances of the builder and director. It then uses the director to construct different types of pizzas by calling the appropriate construction methods. Finally, the builder returns the constructed pizza objects.

```python
# Product
class Pizza:
    def __init__(self):
        self.crust = None
        self.toppings = []
        self.cheese = None

    def __str__(self):
        return f"Pizza with {self.crust} crust, {','.join(self.toppings)}, and {self.cheese} cheese"

# Builder
class PizzaBuilder:
    def __init__(self):
        self.pizza = Pizza()

    def set_crust(self, crust):
        self.pizza.crust = crust

    def add_topping(self, topping):
        self.pizza.toppings.append(topping)

    def set_cheese(self, cheese):
        self.pizza.cheese = cheese

    def get_pizza(self):
        return self.pizza

# Concrete Builder classes 
class MargheritaBuilder(PizzaBuilder):
    def __init__(self):
        super().__init__()

    def set_crust(self, crust):
        self.pizza.crust = crust

    def add_topping(self, topping):
        if topping in ["tomato sauce", "mozzarella cheese"]:
            self.pizza.toppings.append(topping)
        else:
            raise ValueError("Invalid topping for Margherita pizza.")

    def set_cheese(self, cheese):
        self.pizza.cheese = cheese


class PepperoniBuilder(PizzaBuilder):
    def __init__(self):
        super().__init__()

    def set_crust(self, crust):
        self.pizza.crust = crust

    def add_topping(self, topping):
        if topping in ["tomato sauce", "mozzarella cheese", "pepperoni"]:
            self.pizza.toppings.append(topping)
        else:
            raise ValueError("Invalid topping for Pepperoni pizza.")

    def set_cheese(self, cheese):
        self.pizza.cheese = cheese

# Director
class PizzaDirector:
    def __init__(self, builder):
        self.builder = builder

    def construct_pizza(self):
        # Director coordinates the construction process
        self.builder.set_crust("thin")
        self.builder.add_topping("tomato sauce")
        self.builder.add_topping("mozzarella cheese")


# Client who orchestrates the builder and director 
margherita_builder = MargheritaBuilder()
pepperoni_builder = PepperoniBuilder()

director = PizzaDirector(margherita_builder)
director.construct_pizza()
margherita_pizza = margherita_builder.get_pizza()
print(margherita_pizza)  
# Output: Pizza with thin crust, tomato sauce, mozzarella cheese, and None cheese

director = PizzaDirector(pepperoni_builder)
director.construct_pizza()
pepperoni_pizza = pepperoni_builder.get_pizza()
print(pepperoni_pizza)  
# Output: Pizza with thin crust, tomato sauce, mozzarella cheese, and None cheese

``