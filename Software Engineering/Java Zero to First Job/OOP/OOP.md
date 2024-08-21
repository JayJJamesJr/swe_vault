
# What is Object Oriented Programming ? 




# What is an Object ?

An object is a virtual entity with a specific list of properties which can distinguish it from other objects and behaviors


# What is a Class ?



# Functional programming vs OOP

- Functional programming works best where you don't care about the order of the function's execution.

- Object-orientation approach allows you to organize your code and program execution in a structured way.

# Benefits of OOP

- Business Perspective

# OOP Principles

- Inheritance
- Encapsulation
- Abstraction
- Polymorphism

## Inheritance

## Encapsulation

In Java access modifiers exist to facilitate the encapsulation of components.

- `Private` - The strictest form of encapsulation. Limits access to fields and methods only within the specific class.
- `Default (Package - Private)` - Members with default access are only accessible within the same package. Other classes in the same package can access these members, but classes outside the package cannot.
- `Protected` - Accessible within the same package and by subclasses in any package.
- `Public` - Accessible from anywhere.

## Abstraction

## Polymorphism


# Classes & Objects

## What does a class consist of?

- Constructors
- Fields
- Methods
- Initialization blocks
- Nested classes

## Types of Classes

 - Concrete Class -  A class who's methods have implementations
 - Inner Class -
 - Abstract Class -
 - POJO (Plain-Old-Java-Object) - 

## What is an interface? 

An interface is an abstraction that defines a behavioral contract that must be followed by every class that implements it.

- All interface methods are `public` and `abstract` by default.
- An interface can have `abstract`, `default`, and `static` methods
	- An interface can have constant fields. All interface fields are `public`, `static`, and `final` by default
- To define an interface method with a body, use the `default` keyword
- Classes can implement multiple interfaces at once.

## Abstract Class VS Interface

| Abstract Class                                       | Interface                                          |
| ---------------------------------------------------- | -------------------------------------------------- |
| 'extends' keyword                                    | 'implements' keyword                               |
| Can have fields with all possible modifiers.         | All fields are constants.                          |
| Can't be extended simultaneously with other classes. | Can be implemented together with other interfaces. |

## What is a type?

A type summarizes the common features of a set of objects with the same characteristics.
Class is a concrete data structure an group of methods that represent an implementation of the type.


# Inheritance

- ## What is inheritance
	- A description of a new type based on an existing one

- ## Super keyword

	- If a superclass has a parameterized constructor and it's subclass doesn't it'll cause a compilation error because the JVM creates invokes the constructor of the superclass first.

- ## instanceof operator

- ## How to extend classes

- ## Inheritance rules


# Polymorphism

- What is polymorphism
- Method Overriding
- Override vs Overload
- Dynamic binding
- final keyword


# Object Properties

`Native`

`equals`

`hashcode` 


# SOLID Principles

# S - Single responsibility principle
# O - Open/closed principle
# L - Liskov substitution principle

# I - Interface segregation principle
# D - Dependency inversion principle

