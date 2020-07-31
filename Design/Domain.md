# Domain Model
What does the application do?<br>
How does the application do it?


The domain model describes the things that the application works with. If it is a school system, the domain will contain objects representing students, classes, grades, etc. If it is a store, it will contain objects representing inventory, shopping carts, payment, etc.

The domain model describes what the application does and how it works. It also informs the technical architecture as well as hardware and hosting choices. Having a domain model is always a good idea.

Many systems are built without a domain model.
- Some teams do not know how to model.
- Small projects may not need one.
- Modern agile / scrum approaches do not encourage models.

Developers commonly skip the modelling the domain because they feel that they understand it well enough to simply start writing the code. Please do not do this. I have seen too many poorly designed systems in the wild.

## Why you need a model
Most applications have a lot of interlocking parts that must work together. Assembling these parts without a plan will result in sub-par results.

Agile makes the claim that code is malleable and can realize the design incrementally. This is only partially correct. Models are more flexible than code. Models are built wholistically, considering all known features. In contrast, Agile projects build the model one feature at a time. They eventually arrive at a model, but it takes more work.

Would you build a house without a plan? If it is a dog house then no plan is needed. If you are building a [Marina Bay Sands](https://www.marinabaysands.com/) hotel, then you absolutely need a design and some careful engineering. Software is not that different.

A the domain object model need not be detailed nor comprehensive. For iterative approaches, the model should be light and minimal. It is only a starting point that shows the basic outline of how the system will eventually look.

Here is one technique for creating a domain model. It is a bit old-school, but it works. Feel free to scale it down if you want.

## Context
List all the types of users of the system. List external systems that exchange data with the system. This is a [UML Context Diagram](https://en.wikipedia.org/wiki/System_context_diagram). It sets the universe in which the system will operate.

Be sure to consider:
- Administrators that monitor the system
- Support people that backup data and perform diagnostic work
- Search engines that catalog the site (SEO)
- External data sources and services (e.g. maps, payment)
- Hackers ??

## Stories
Consider an actor to be any user or system that can initiate some action within the system being developed. Look at all the actors. Think about their needs and how the system might serve those needs. Each one of these is a Story. It should be worded using words the user would understand.

At this point you can launch into a scrum-like project using the stories. This is fine for a small system. For larger system you need at least a minimal simple domain model to start - so continue to the next steps.

## Use Cases
Look at each story and determine what are it's goals. Each goal is a Use Case. Look at each Use Case and determine what steps the system must do to support it. These are Scenarios. NOTE: The relationship between Stories and Use Cases is nuanced. Read up on it before diving in.

- **Main Scenario** : Write down the main sequence of steps that describe the most common interaction between the user and the system.

- **Extensions** : Look at each step and determine common ways that it might fail. Then think of steps that would recover from the failure. Sometimes the failure can be overcome, sometimes reducing the damage is all that can be done.

- **Variations** : Look at the use cases for situations where there are multiple options. For instance, payment by credit card or by PayPal. These are variations and they will have different steps associated with them.

- **Sub Scenarios** : Factor out repeated bits into their own sub units.

The trick here is knowing when to stop. Add enough detail that you have covered all of the difficult cases. For tools, any text editor will do.

## Sequences
Look through the scenarios. Locate the nouns and verbs. The nouns are canditate objects; the verbs can become methods on the object that receives the request. Build a [UML Sequence Diagram](https://en.wikipedia.org/wiki/Sequence_diagram) for each scenario. These diagrams will implicitly contain your domain object model. A good design tool, like [Sparx](https://sparxsystems.com/) can help a lot.

Check:
- All of the actors initiate use cases.
- All external systems are included in sequences.
- Applicable relationships are known or can be discovered*.

*This means that if object A calls method on object B, then A knows about B or has a way of discovering it.

## Domain Object Model
At this point, a [UML Object Model](https://en.wikipedia.org/wiki/Sequence_diagram) can be easily derived from the sequence diagram. It should be technology agnostic. Apply design patterns to make the model more aligned to the technology you will be using. 

From here:
- Create initial data model from the object model.
- Create initial code stubs from object model.

There are tools that can automate this.

## Test Cases
- Test cases can be mostly copied from the use cases. 
- Add unit tests based on what is coded.
- Add a unit test for each edge case.

Additional tests can be derived from these models

- Verify code syntax : compiler
- Verify code semantics : lint
- Verify code supports design : unit tests
- Verify design supports architecture : integration tests
- Verify architecture supports requirements : user / end-to-end tests

## Move On
At this point fill in the methods / code and you will have a starting point for the project. Have fun!

[Next> Application Design / Wish List](WishList.md)