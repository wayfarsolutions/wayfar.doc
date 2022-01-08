# Clean Architecture

WayFar template was designed to support to build fully modular application where every feature may have entities, services, database integration, UI components and so on. It provides an infrastructure to make Clean Architecture easier to implement.

## What is Clean Architecture ?

Clean architecture is a category of software design pattern for software architecture that follows the concepts of clean code and implements [SOLID principles](https://www.educative.io/blog/solid-principles-oop-c-sharp).

It’s essentially a collection of best practice design principles that help you keep **business logic**, or domain logic, together and minimize the dependencies within the system. If followed, clean architecture lets software architects with decoupling components so they become isolated enough to be durable and easily changed without remaking the system.

&#x20;(s_ource:_ [_https://www.educative.io/blog/clean-architecture-tutorial_](https://www.educative.io/blog/clean-architecture-tutorial)_)._

![](../../.gitbook/assets/CleanArchitecture.jpg)

## Layers and building blocks

&#x20;In Clean Architecture: The application is built around an independent object model. Inner layers define interfaces. Outer layers implement interfaces:

### Entities

Entities are the core layer, it can be an object with methods or just a collection of data structures and functions. They encapsulate the most general or higher-level and are therefore the least likely to change due to a change to an outer layer.

### Use cases

Use Cases is the second domain layer. It defines application-specific business rules. They encapsulate and implement all of the approved use cases for the application.

### Interface adapters

This layer is responsible for adapting the user input, and uses cases output into a suitable format that can be usable by inner and outer layers respectively. The adapters layer is the effective boundary between inner and outer circle layers.

### Framework and drivers

Framework and Drivers is the presentation layer that is usually composed of frameworks and tools such as databases, web frameworks, and so on. This layer doesn’t feature much code but rather use built-in objects and methods specific to the current framework.

## Benefits of Clean Architecture

* Highly testable
* Flexible
* Framework independent
* Database independent
* UI independent
* Reusable layers
