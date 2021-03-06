# Technologies and tools

No web application nowadays is written from a scratch.
There are various tools to fasten up the development process and make it easier.

In this section, it is stated what tools and libraries are used for the project.
There are several issues that are usually solved by an existing library.
It is discussed in this chapter and not in the implementation, because in some cases, the used tools affect the architecture or the components of the designed system.

Since there are several system components, that can be designed using existing libraries and they have far lesser overall effect on the system^[Compared to the Git SSH authorization layer e.g., which required more structured analysis], the details of the libraries and its alternatives are abbreviated.

## FE framework

FE of the application is no more a trivial jQuery script with a a few user interactions in the browser, such as it was fairly popular several years ago.
More and more tasks are expected to be performed inside the browser for better UX and more dynamic effect.

This also calls for a solution for building complex FE applications.
There are few popular solutions for FE frameworks, such as Angular 2, React and Vue or Ember.

React is chosen, being fairly the most popular among its alternatives and fast and easy to use, thanks to the JSX syntax and its virtual DOM.

## SSR

Many websites rely too much on the FE technologies, resulting in a monolithic so-called _single-page applications_.
When majority of the logic happens in the browser and the server's HTML response contains (more or less) only the `<script>` tag, several issues arise.
The hardest problems face the clients that cannot interpret JS.
This might seem banal, because generally speaking all the users browse the web with a browser which JS engine.
The issue becomes more realistic, when non-user agents are considered, such as search engine spiders for instance.

This issue is tacked by several libraries, from which Next.js [@next] with native support for React is selected.

## FE State container

Facebook introduced [@flux] the Flux architecture in 2014 to solve complexity of MVC's nontransparent dependencies for complex systems with many models and views via a linear unidirectional data flow.
The main idea behind Flux is to linearize uncontrolled flow between models and views through a single component.

This component is called _dispatcher_.
It consumes _actions_ and updates the _store_ as a reaction.
The _store_ defines the _view's_ state (_view_ renders data from _store_), and can pass new _actions_ to the dispatcher.
This flow is displayed on the diagram @fig:design:flux.

![Design: Flux architecture](./src/assets/diagram/flux){#fig:design:flux width=65%}

Flux is a general architecture concept and though having its Facebook's implementation of the core modules, there are many other existing options.

One of those is Redux [@redux], which is used in the project.
There is also a Redux-Saga [@redux-saga] extension for asynchronous action consumption (synchronous consumptions are handled by so-called _reducers_^[Modules that produce new state based on the previous state with regard to dispatched action]) and works well with Next.js.

## Git library

While there are also many libraries for working with Git repositories for Node.js, NodeGit [@nodegit] is selected.
NodeGit is a binding to a popular C library libgit2 [@libgit2], an implementation of core Git methods.
NodeGit is used for repository abstraction and manipulation.

## Node.js web application framework

Express.js is used for the BE application as routing service and HTTP server with middle-ware management.
