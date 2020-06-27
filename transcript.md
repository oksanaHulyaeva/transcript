Hello there. Thank you for watching this video and today we are going to talk about structural patterns of programming, or - to be more precise - about the most popular and frequently used ones.

#### I-II slide
So what is pattern in general?  It is customary to call with this term some kind of common architectural solutions that are applied in software design in general and in Javascript web applications in particular. A pattern usually represents an 'out of the box' solution that can be adapted to suit our own needs. It is a specified way for solving the same type of problems, a template which can be used in quite a few different situations.

The main benefits we expect to get from design patterns are the following:

* The first one is – the solution must be easily reusable. In other words, it can be modified for solving multiple problems, as it is not tied to a specific situation.
* The second one is – the solution must be proven. That means it must be approved by many developers before you, so you could be certain that it is  really optimized and works efficiently.
* And besides that, patterns are usually expressive – they can express a large solution quite elegantly and let to reduce the amount of code.

#### III slide
Design patterns can be categorized in multiple ways, but the most popular one is the following:
*	Creational design patterns
*	Structural design patterns
*	Behavioral design patterns

And in this presentation we are going to consider particular structural patterns.

#### IV slide
So what are structural programming patterns? This is a kind of patterns that deals with object relationships. They help ensure that when one part of a system changes, the entire structure of the system doesn't need to do the same. The most popular patterns in this category are:

#### V slide
Composite, Facade, Flyweight, Adapter, Decorator, Proxy, Bridge. All types are listed in order of frequency of use. The first three items marked in red are the most popular and used, that’s why we will consider them in more detail.

#### VI slide
**Composite** – one of the most useful and efficient patterns. It allows us to treat both individual and compound items in a uniform way. It is really cool, cause we can apply the same behavior regardless of element’s structure and amount. Each item in the collection can hold inside other collections, creating deeply nested objects, but thanks to Composite pattern we can process it in absolutely same way.

A tree structure is a perfect example of a Composite pattern. The nodes of the tree can be simple (leaf nodes) or compound (a subtree of nodes). All nodes in the Composite pattern share a common set of properties and methods which supports individual objects as well as object collections. This common interface greatly facilitates using of recursive algorithms that iterate over each object in the Composite collection.

So let’s consider a particular example of usage. Here we have a main class *Equipment*, which has some methods for getting and setting values, and 2 subsidiary classes – Engine and Composite, which extend methods from the Equipment (here Engine is an example of leaf node, Composite – of compound node). The both classes have a method *getPrice()*, but it works in different way. In first one it just returns a price value, in another one it works recursively and returns final price of all nested items and objects.
As a result we can apply the method *getPrice()* to any type of items despite their structure, what is very convenient.

#### VII slide
The next one pattern is really useful and extremely wide used approach in software design. The main idea of **Facade** is providing a comfortable and unified higher-level interface for a whole quantity of complex subsystems. So it hides the complexity of the business objects and their interactions details from clients as well as a real factory’s facade hides some manufacturing processes from customers. Why? Because clients don’t need to know how it works "under the hood", they just want to get the product or feature as easily and comfortably as it possible.

Facade is a structural pattern which can often be seen in JavaScript libraries like jQuery and others, where we can use some simple public methods without diving into complex and confusing business logic they contain inside.

Another area where Facade is widely used is refactoring. Suppose you have a confusing or messy set of legacy objects that the client should not be concerned about. You can also hide this code behind a Facade.

So let’s see how it works.
Here we have some complex class with a pretty quite a lot of methods. The second class is *ConveyorFacade*,  that can receive some object (with its own methods) as a parameter. This class contains just one method *assembleCar()*, which consistently calls some methods of the received object to build entire car as a result.

So if we create a new instance of *ConveyorFacade* with a new *Conveyor* as a parameter we need just one more call to get our car assembled – all we need is too invoke the method *assembleCar()* for our new conveyor  object. Convenient isn't it?

#### VIII slide
And the last – but not least – method is a **Flyweight**.

The Flyweight pattern is a classical structural solution for optimizing code that is repetitive, slow and has inefficient data organization. Flyweight helps to optimize the usage of memory in applications by sharing as much data as possible with related objects. Shared flyweight objects have to be immutable, cause they represent some common for many others objects properties.

There are two ways in which the Flyweight pattern can be applied. The first is at the data-layer, where we deal with the concept of sharing data between large quantities of similar objects stored in memory.

The second is at the DOM-layer where the Flyweight can be used as a central event-manager to avoid attaching event handlers to every child element in a parent container we wish to have some similar behavior.

Let’s look at the scheme. The main elements here are the *Client*, *FlyweightFactory* and *Flyweight* object itself. The Client calls into FlyweightFactory to get flyweight objects. The FlyweightFactory serves for creating and managing Flyweight objects and the Flyweight maintains specified data to be shared across the application.

In our example of code we can see how factory-class AutoFactory creates new instances of Auto. The main principle of Flyweight pattern has been realized in method *create()*, which implements a uniqueness check before creating a new instance. If *this.models* object exists and has a *name* property, the method just returns already existing object. As a result, after all these 4 calls we will have three unique objects.
Such approach helps to avoid repetitions and optimize application’s memory.

It is a very simple example, but Flyweight is a really great and widely used solution. It is often applied in utility type applications such as word processors, graphics programs, network apps and even in JavaScript engine itself which maintains a list of immutable strings that are shared across the application.

So, we’ve just studied three the most popular structural solutions, hope it was helpful, thanks for watching!
