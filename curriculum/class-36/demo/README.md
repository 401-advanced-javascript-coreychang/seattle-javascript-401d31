# DEMOS - Context API

## Execution

Demos are provided in the `demo` folder in the guide repository. They are created with `create-react-app` and are suitable to install and run locally or at [Code Sandbox](http://codesandbox.io).  

At Code Sandbox, simply create a new app using "Git Hub" and point it at the the appropriate demo folder and it'll spin the app up for you. Saves a lot of time and also shows the students the value of doing quicker "POC" style work in an online IDE and then executing production code in their actual IDE.

## `context-api`

For this demo, the actual code being written is relatively small, but the concept is again pretty large.

Definitely spend plenty of time in pictures, drawing out the connections between the context provider and the components before you code it out. This should give you a good reference point to refer to as you write out the code.

The demo only needs a simple context provider with one bit of state and one modifier method. That will be enough to sell the concept and give the students the tools to build out their counter application.

Note that the demo has a repeated `<section>` in the render so that you can demonstrate the 2 ways to use a single Context

* With a `<Context.Consumer>` wrapper, which requires you to use a function() that receives context
* Using `static contextType` to set `this.context`

Make note that `contextType` only works if you have a single context being used in the component.

The Editor demo is split into multiple components so that you can show:

* 2 components sharing the same context
* Using static context
* Using the Provider functionality to use context


## `context-api-refactored`

This second demo is more advanced, and makes use of multiple contexts

The primary takeaway here is that you can no longer use `contextType` if you're referencing them in the same component.

For this reason, talk about and look for opportunities to refactor and use multiple, targeted components to use each context.

In this example, we're using the `Theme` context in main to drive style and also in the editor so that we can edit those settings and save them back to state.

## Lab Prep

Students will need to employ both methods to complete the lab assignments.
