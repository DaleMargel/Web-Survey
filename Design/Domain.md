# Domain Model
Before we can do anything, we must know what the application does.

The domain model is the underlying model that the application emulates. A school system will contain (abstractions of) things like students, classrooms, etc. A bankng system will contain account and transactions.

Why do we need this?

Many systems are built without a domian model. They work fine for a while, but over time disorder creeps in. With no blueprint to follow, growth is chaotic and the application becomes harder to maintain. A domain model keeps the code focused on requred features and minimizes the code needed to implement those features.

There are many ways to do this, but all of them are a form of "divide and conquer". The model does not need to be comprehensive, just enough to make sure you start on the right track.

Here is one technique.

## Context
List all the types of users of the system. Add to this other systems that ours will send data to, or get data from. This is a UML Context Diagram. It sets the universe in which the system will operate.

## Stories
Look at the various types of users in the domain model. Think about their needs and how the system might serve those needs. Each one of these is a Story. It should be worded using words the user would understand.

At this point many projects launch development efforts based on the stories. This is fine for a small system. For larger system you need at least a simple domain model to start - so continue to the next steps.

## Use Cases
Look at each story and determine what the system must do to support it.These are use cases. Add to this any system that requests data from your system.

- Main Scenario : Write down the steps that describe the most common interaction between the user and the system.

- Extensions : Look at each step and determine common ways that it might fail. Then think of steps that would recover from the failure. Sometimes the failure can be overcome, sometimes it cannot.

- Variations : Look at the usecases for cases where there is more than one way of doing the same thing. For instance, payment by credit card or by paypal. They accomplish payment but in different ways.

- Sub Scenarios : Some use cases are repeated in many other. Signing into a system is one example. Factor these out into prerequisites or as a part of the parent use case.

The trick here is knowing when to stop. Add enough detail that you have covered all of the difficult cases.

## Sequence
Look through the use cases. Look at the nouns and verbs. The nouns will likely become objects and the verbs will become methods on the object that receives the request. Use a UML Sequence Diagram if you want. 

When one object must interact with another, it must know about it. Determine how it will know or find out about it.

Check - account for:
- All of the use case nouns and verbs.
- All of the users and systems in the context diagram.

## Objects
At this point, you will have an object model. It should be technology agnostic. Apply design patterns to make the model more aligned to the technology you will be using.

## Test Cases
Test cases can be modeled from use cases in most cases. Add unit tests. Each one should test a logic flow or a single edge case.

## Move On
Now that you have decided what the application needs to do, we need to look at how we are going to do it.

[Next> Application Design / Wish List](WishList.md)