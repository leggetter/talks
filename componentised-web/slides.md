# The State of the
# Componentised Web
<br />
#### Phil [@leggetter](http://www.leggetter.co.uk)

Note:

- Building apps from components: nothing new
- Web Components on the horizon: component-based dev
- Benefits
- Existing technologies
- Future

--

## What are Components?

* Smaller piece of a larger app
* UI
* Logical unit

Note:

- Semantic Overload

--

#### UI Components

![](img/components.jpg)

--

#### UI Components - Simple

![](img/gmail-components.png)

--

#### UI Components - Composed

![](img/gmail-components-composed.png)

--

### Service Components

* XHR/AJAX
* Data Synchronisation
* Logging
* In-App Messaging
* Contacts Service
* Email Service
* Chat Service

--

## Why Build Components?

--

### Modular

<blockquote>Conceptually, modules represent a <strong>separation of concerns</strong>, and improve <strong>maintainability</strong> by enforcing <strong>logical boundaries</strong> between components. Modules are typically incorporated into the program through <strong>interfaces</strong>... The <strong>implementation</strong> contains the working code that corresponds to the elements declared in the interface.</blockquote>

<small>Source: <a href="http://en.wikipedia.org/wiki/Modular_programming">en.wikipedia.org/wiki/Modular_programming</a></small>

Note:

- Semantic overload again!
- Modules, components, widgets etc.
- Components ~= Modules

--

### High Cohesion

<blockquote>the degree to which the elements of a module belong together</blockquote>
<small>Source: <a href="http://en.wikipedia.org/wiki/Cohesion_(computer_science)">en.wikipedia.org/wiki/Cohesion_(computer_science)</a></small>

Note:

- Arghhhhhh! Software Engineering buzzword bingo!

--

### High Cohesion - Example

![](img/asset-structure.png)

Note:

- We can do the same with functionality

--

### Reusable

<!-- .slide: data-background="img/gmail-components.png" data-background-size="100%" data-state="black-bg alpha-bg" class="dark" -->

* DRY
* Consistent UI

--

### Reusable
#### A word of warning

--

### Interchangable

* Same interface/contract
* Same functionality
* Easily swap

--

### Composable

--

## Building Components Now

--

## Example

```js
  <my-avatar service="twitter" username="leggetter" />
```

--

### Angular

<a class="jsbin-embed" href="http://jsbin.com/lacog/2/embed?html,output">JS Bin</a>

--

### Ember


<a class="jsbin-embed" href="http://jsbin.com/nawuwi/4/embed?html,output">JS Bin</a>

--

### React

<a class="jsbin-embed" href="http://jsbin.com/qigoz/5/embed?html,output">JS Bin</a>

--

### ReactiveElements

<a class="jsbin-embed" href="http://jsbin.com/qigoz/7/embed?html,output">JS Bin</a>

--

## The Future:
## Web Components & Beyond

--

* Custom Elements
* Shadow DOM
* HTML Imports
* Templates

--

### Platform.js

<a class="jsbin-embed" href="http://jsbin.com/pihuz/4/embed?html,output">JS Bin</a>

--

## Other Polyfils

* [bosonic](http://bosonic.github.io/)
* [W3C Custom Elements Polyfil](https://github.com/WebReflection/document-register-element#document-register-element)

--

### Polymer

<a class="jsbin-embed" href="http://jsbin.com/gukoku/2/embed?html,output">JS Bin</a>

--

### X-Tag & Brick

<a class="jsbin-embed" href="http://jsbin.com/wexiz/2/embed?html,output">JS Bin</a>

--

## Component Inter-Communication

--

## Conclusion

--

# Thanks!
# Questions?
<br />
#### Phil [@leggetter](http://www.leggetter.co.uk)
#### [BladeRunnerJS](http://bladerunnerjs.org)
<br />
#### [j.mp/realtime-sotr14](http://j.mp/realtime-sotr14)
