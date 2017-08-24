# UNPKG -- Michael Jackson (React)

- Use CDNs from https://unpkg.com (hosted on CloudFlare) instead of pulling in React or whatever pkg from npm/node_modules
- Allows webpack of whatever module loader to use the CDN references for a pkg (react, jquery, etc) vs adding to bundle.js and hosting locally

## Script Type Module

*!Caveat! Chrome 61, Safari ?*

EXAMPLE

<script type="module">
  import * from 'd3?module';
</script>

adding `?module` at the end of the moudle/package name will prepend the `https://unpkg.com/` to the module name and append any other params at the end of that module name with babel transforms

500+ request in a matter of seconds. Cache is king.

____________________________________________________________________


# D3 & React -- Shirley Wu (Freelance)

## DESIGN NOTES

Cool heat map visualizations categorizing/grouping by color

____________________________________________________________________


# IOT -- Devon Lindsey (Apple)

## NFC with August

1. August
2. NFC chip
3. RaspberryPi


____________________________________________________________________


# Back to React: The Story of Two Apps -- Michael Chan (Learn React)

## React, the missing piece

2013
High tolerance for JIT Solutions --> Great Maintainability

2015
React++  --> too many libs & dependencies

2016-2017 --> Javascript Fatigue

## 5 Liberating Constraints

1. Know who's driving
- Too many cooks in the kitchen (frameworks)
- What role does React play in your app (Rails or React)

2. Optimize for change
- Abstracting is a waste of time, make HOCs that work
- Testing components prevents future optimization
- Can't predict performance problems

3. Know your shapes/Master the patterns
- Nested components (knowing vs unknowing)
  Allows many components to be dumb
- HOC vs Callbacks
  BOTH!

4. Avoid the edges
- "Don't forget it's not the edge that's bleeding, it's you"

5. Partner don't depend
- Guard your stack
- Choose tools you can master (partners)
- Stop delegating (to open source libs)
  If you npm install, own it -> it's your code -> master it -> don't complain


____________________________________________________________________


# What WebAssembly means for React -- Lin Clark (Mozilla)

## Benefits

1. Compile down to binary
2. Extreme performance for Native apps (more so than React Native)
3. Allocate function closures into WA's memory in order to compile down to binary

## Stuff to know

Ability to pass in JS closures to WA (function pointers)
                  |
                  |
                  V
Allow WA and JS to pass values back and forth
                  |
                  |
                  V
Prevents Memory leaks (security bonus)

## Other Bennies
1. Reusability to code
2. Run faster in browser?
- parse
- compile & optimize (self optimization by memory allocation)
- re-optimize (not done by JS alone as a Memory Managed Language)
- execute
- garbage collection
          |
          |
          V
So does it make a React browser apps run faster?
- overhead managing two configs (.js & .wasm)
- communication between JS & WA (not optimized yet -- but only nano seconds -- will eventually add up)

## Forward thinking
- 3-6 months these optimizations are gonna be blazing

## Hybrid Solutions
What if you make WA components ANDDD React Components?

## Threading
Parallelizing --> Concurrency between sharing array buffers


____________________________________________________________________


# Layperson's guide to React Fiber - Ben Ilegbodu (Eventbrite) -- SquatsGuy

## Fiber
- Watch Lin Clark's vid -- a cartoon intro to Fiber

## V16
- 20% smaller
- Can return an array of adjacent elements now instead of React throwing error
  EX.
  _renderContent() {
    return ([
      <nav>...</nav>
      <main>...</main>
    ]);
  }
- Check out React Aux --> component wrapper that relieves tag bloat

## Error Handling

- Error Boundaries
- New life cycle event (componentDidCatch)
  EX.
  <ErrorBoundary>
    <BuggyComponent /> (this will prevent the app from failing)
  </ErrorBoundary>
- Suggestion: Wrap Router with an `<ErrorBoundary>` component


## MOARRR UPDATES

- No more data-reactid ** need to update Retul
- ReactDom.hydrate(...)
- Async Scheduling (turned off -- will exist in another version........... but... workaround http://www.benmvp.com/slides/2017/reactrally/fiber.html#/)

____________________________________________________________________


# ReacTex: using React Native and Neural Networks to recognize handwritten equations -- Bonnie Milián
- AI, ML (Machine Learning), DL (Deep Learning)

## Get Involved With APIs and other tools
- IBM Watson
- Google Cloud

### Step 1: Understand how these tools behave
- DIY projects


### Step 2: Learning Materials
- Udacity
- Coursera

## Neural Network (types of learning)
- Supervised vs. Unsupervised


____________________________________________________________________


# Twitter Lite, React Native, and Progressive Web Apps -- Nicolas Gallagher (Twitter)

'A web framework without a DOM or CSS' -- Nicolas Gallagher
React is moving towards becoming a platform than a framework.

## WebApp Pain points

1. CSS

## The Power
1. Simple
2. Responsive
3. Events (touch, swipe, etc)
4. Accessibility APIs


## React Native for Web Dev
- React Native built on top of ReactDom
- StyleSheet API (subset of CSS)
  StyleSheet.create({
    'display': 'block',
    ...
  });
- React Native Styles vs CSS
  React Native Styles > CSS -- the more specific native style prop wins where CSS is order of styles rendered

# React Dev Tools
- With the React Dev Tools & Jest Snapshots, we can easily create a stack trace of how to resolve or view each rendered result of a RN component

# Accessibility
- Using ARIA roles and AccessibilityTraits

## My Thoughts
- so instead of optimizing class names and architecting css modules and relational objects, we abstract combinations or more atomic descriptions of how individual components are displayed #atomic rulez


____________________________________________________________________


# React-ing htmlFor=empathy -- Jana Beck (Stitch Fix)

Checkout Data Science Algorithms @ http://multithreaded.stitchfix.com/
Checkout Eye Tracking Platform @ https://webgazer.cs.brown.edu/

## Project

A side project where speaker used technologies to use Partner Assisted Scanning with the web app and the face detection platform that will recognize communication using an alphabet chart when user blinks.

- Using WebGazer & ReactJs
- Build algorithms to collect the data via gesture and data collection platforms
____________________________________________________________________


# Redux + ServiceWorker = Offline React -- Zack Argyle (Pinterest)

## Service Workers
Go check out fetch race method
  --> parallel request on an old device can be slower than fetching over network due to old hardware

## Application Shell
The googs lika da app shells (they recommend server rendering -- SEO)

## Middleware (Redux)
Redx is king

## Demo
Saving the app shell, js, and css upfront via the service worker creates a seamless experience online or offline
