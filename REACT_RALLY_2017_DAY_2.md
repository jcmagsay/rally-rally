# We All Started Somewhere -- Preethi Kasireddy (React)

- Bell curve chart for entry to learning
- Preethi -> https://medium.com/@preethikasireddy
- TJ Holowaychuk -> https://medium.com/@tjholowaychuk

## Reflections
`
Don't forget what it was like to be an entry level dev. Concepts didn't always come as easy as they do now.
`
____________________________________________________________________


# Convergent Evolution -- Evan Czaplicki (ElmJS)

## Elm vs. React

- Elm -> immutable & functional
- Elm -> forces patterns -- good and bad ways to use it
- Both have the concept of static data analysis

## Reflections
`
Super tight. Definitely need to jump on the Elm train for comparison. The amount of time spent into the logging alone gained immediate respect.
`
____________________________________________________________________


# So how does Babel even work? Let's create the JSX transform to find out! -- Henry Zhu (Behance)

- 'Compiler that compiles JS to JS' -- lol
- Look up AST (Abstract Syntax Tree)
- Compile PHP to JS -> https://babeljs.io/php/

## ASTExplorer
- Go to astexplorer.net\
- Watch ES2015+ compile to ES5 real-time

## Contribute
Contribute at https://github.com/babel/babel/blob/master/CONTRIBUTING.md

## Future
- TC39 needs feedback to control the future

## What it means to be a contributor?
- Just do it
- There's no right way
- `Code doesn't matter, people do`
- Just show up
- Open Source community will help you and the code better

## Reflections
`
They need help with contributions. Give back!
`
____________________________________________________________________


# Scaling My First Enterprise React App! 🐙 -- Jennifer Van (Capital 1)

## Hallmarks of enterprise products?
1. Persist
2. Grow
3. Testing

## Scaling Properly
- Scaling means that apps are still performant

### But how?
1. Define presentation vs container components
2. Utilize performance timeline to determine bottlenecks
   append ?react-perf
3. Remove unnecessary renders
   Utilize `shouldComponentUpdate` to short circuit unnecessary renders
4. Prioritize network calls
   Go to network tab and sort Priority
   - Priority of rendering elements
   - Escalate  text priority (add rel="preload" to whatever resource is being fetched -- css & js)
     a. High: HTML, Styles, AJAX/

## Keeping Redux fast
1. Set state is okay
2. Connect @ multiple components
3. Normalize state shape (
   - each type of data gets its own table
   - each object gets its own id as a key

## File Structure
`
Root
  |_ JS
      |_ Components
          |_ Presentation
          |_ Container
`

## Documentation

Write code that is understandable and comprehensive, but when all else fails, make sure complex logic that is not immediately comprehensive is documented.


## Static Code Analysis

Use TypeScript and linters


## How to prevent growing pains when user base grows

### Accessibility
These are common forgotten users

## Testing for Accessibility
1. Keyboard testing
2. Assistive Technology Support (Screen Readers)
3. reactrally

## Testing in React/Redux

JUST DO IT

Check out:
1. Enzyme
2. Jest
3. Mocha

## Reflections
`
Scalability should have a plan from the beginning of the project life cycle. Alleviate the pain before it even begins.
`

____________________________________________________________________


# Everything is a plugin!! Mastering webpack from the inside out - Sean Larkin (Microsoft)

## Tapable
Used to create webpack plugins
A class object that extends tapable

## Walk through source code (WebPack)
1. Compiler -- `import webpack as 'webpack';`
2. Compilation -- webpack(config)
3. Create dependency tree -- what requires what
4. Resolver -- resolves paths and makes sure things exist`
5. Module Factory -- creates module
   - Takes successful resolv requires
   - Collects source for file
6. Parser -- parses (I can haz ASTs)
   - Takes mod obj turn into AST to parses- find all req. import and create dependencies
7. Template -- data binding for your modules
   - Creates code that is in your bundles
   - Compress into a chunk (chunk template)
   -

## How webpack guilds the graph
Steps 1-7 and then the tree is created

## How does it get served?
- Init Compiler
- Compile the configs
- Get everything you need and everything the thing you need requires
- Resolve all the things you required and are dependent on the things you require
- Make all the things available
- Parse all the things
- Put the things into groups (chunks)


## Why should you care what's under the hood?
GitHub: https://github.com/TheLarkInn/everything-is-a-plugin

## Webpack3
opencollective.com/webpack

## Reflections
`Sean is really great at karaoke. He jammed on the air guitar so hard. This presentation was amazing. As an avid WebPack user, I had a great understanding of the tool before, but more so now. Sean did a great job breaking down the flow of what happens when a WebPack bundle is created.`

`TODO: I need to buy WebPack Swag`


____________________________________________________________________


# GraphQL IRL -- Cameron Matheson (Instructure)

## What is it?
A QL that contains:
1. Types
2. Resolvers

## GraphQL 4 reel
Use GraphIQL https://github.com/graphql/graphiql for deep viewing your queries

Some problems:
1. Over fetching
   You can resolve by preloading
2. Relay

## Reflections
`Talk was great. As a GraphQl user I enjoyed seeing and understanding some painpoints and how to alleviate them -- particularly over-fetching.`

`TODO: Think about ways to improve over-fetching from the Relay side vs. the GraphQl side`

____________________________________________________________________


# Demystifying setSet() -- Justice Mba (Vconnect)

## Set State Flow
1. Declare state in component
2. Update values
3. Reconciliation of new value

## Batching

## Functional setState
this.setState((prevVal, newVal) => {

})


## Reflections
- `Wow! All the way from Nigeria. Props Justice.`
- `I loved passing a function vs. a value for async updates. Great stuff!`

____________________________________________________________________


# Infinitely Better UIs with Finite Automata -- David Khourshid (Microsoft)

## Bottom Up Approach is problematic

Bottom up approach can be defined as

One Event --> Creates a fuck ton of business logic

- diff to understand, test, enhance
- contains bugs
- features are hard

## User Interfaces as Graphs

UIs don't have to always be trees, they can be graphs.


## possible states
```
 (green)  Deterministic
(yellow)  Finite
 ( red )  Automata
```

## Graph Theory

### PacMan

Ghosts have 3 states
1. default
2. active - after PacMan eats a pill
3. dead - after PacMan eats ghost
```
   ________________________
  /                        \
  |                         |
  V                         |
default -> active -> dead _/
             |
             V
           default
```

## Finite State Machines (FSMs)
Shortest path to get to each state

## Problems with FSMs


## Statecharts
Hierarchical FSMs
 ________________________________________________________
|                                                        |
|                                                        |
|     (green)  Deterministic                             |
|     (yellow)  Finite                                   |
|     ( red )  Automata                                  |
|                                                        |
|                                                        |
|________________________________________________________|
            |
            |
            |
      (flashingRed) -- power outage

## XState

Concurrent state handler

`npm install xstate`

## Reflections
```
Bro bro was legit. I enjoyed this talk and wish it could've kept going.
Short circuiting and finding the path of least resistance is something
I need to start thinking about before implementing solutions.
Graph & tree relations are amazing and will absolutely spike the
performance of an app.

TODO:
1. Add this to project kickoff checklist
2. Work with UX team to create workflows that ease this thought process
```
____________________________________________________________________


# Start a conversation between browser windows - Cara Kuei (NFL)

NFL React Projects
- ReactWildcat
- ReactHelmet

## Postmessage

More info @: https://developer.mozilla.org/en-US/docs/Web/API/Window/postMessage
- Event system
*Caveat: all events are in global scope with PostMessage* -- not to different from most pub-subs/event systems

## NFL: Using with PostMessage with React

*Background*
Legacy pages are not React, iframes are used to allow new to be hosted with legacy


### Embeddable Content

Layers
1. Legacy package
2. <iframe>
3.

### HTTP -> HTTPS

Using HOCs to pass complex data that will drive the ability for the legacy app and new React to communicate

### How does PostMessage help?

#### Workflow before PostMessage
1. Create a new entry in CMS for hero
2. Choose logo
3. Save
4. Refresh
5. Deets show up

#### Workflow after PostMessage
1. Create a new entry in CMS for hero
2. Edit alt tag
3. Save
4. Deets show up


## IRL Example

### postMessage Signature

`otherWindow.postMessage(message, targetOrigin, [transfer]);`

### What you need

1. Publishers
2. Subscribers
3. Event Handlers
   Receiver that will check namespace

### Issues
1. Might miss a message
   Async messaging that ties into React's life cycle hooks


## Takeaways
- elegant simple Application
- well structured message
- being async
- usable in react
- allows large migrations from legacy to new features

## Reflections

Cool implementation. I feel weird about pub-sub and event systems in general
because of arbitrary global variable, but I'd like to test out the name-spacing
with React components to see if it works for me. I still don't like the idea of
event systems with React because that's not really the "React way" however I
admire and appreciate this solution given the constraints.

```
The React Way
------------------------------
         __ HOC __
        /         \
       /           \
      /             \
  Component1    Component2
------------------------------
```
`Data can be passed from Component1 to Component2 just by relation of being a descendent from the same component`


____________________________________________________________________


# I want you to contribute to open source - Max Stoiber ()

## Advice

1. Solve your own god damn problems
2. Open Sourcing helps yourself
   - Future you ain't got time for that
   - Worst Case Scenario: You fix your own problem for the future
3. *Pro Tip*: Ask yourself "Can I make it Open Source?"
   - Not everything can be
   - Does it exits?
4. Write a blog post
5. Open a PR to update other's open source libraries
   - Sometimes documentation updates are all an open source lib needs
6. Know your limits
   - 0 to 60 isn't possible overnight
   - Start small

## Steps

1. Solve your problems
2. Generalize solution
3. ???? -- to much to mention
4. Profit

## Examples
1. Social Media Share Buttons@
   - https://github.com/mxstbr/sharingbuttons.io
   - http://sharingbuttons.io/
2.

## TODO
1. Update Atomic's documentation on using Webpack2
2. Webpack and SASS working with HMR
