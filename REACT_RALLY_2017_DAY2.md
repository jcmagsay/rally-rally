# We All Started Somewhere -- Preethi Kasireddy (React)

- Bell curve chart for entry to learning
- Preethi -> https://medium.com/@preethikasireddy
- TJ Holowaychuk -> https://medium.com/@tjholowaychuk

____________________________________________________________________


# Convergent Evolution -- Evan Czaplicki (ElmJS)

## Elm vs. React

Elm -> immutable & functional
Elm -> forces patterns -- good and bad ways to use it
Both have the concept of static data analysis

____________________________________________________________________


# So how does Babel even work? Let's create the JSX transform to find out! -- Henry Zhu (Behance)

'Compiler that compiles JS to JS' -- lol
Look up AST (Abstract Syntax Tree)
Compile PHP to JS -> https://babeljs.io/php/

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
```
Root
  |_ JS
      |_ Components
          |_ Presentation
          |_ Container
```

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
