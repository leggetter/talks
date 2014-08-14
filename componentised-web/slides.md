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

<!-- .slide: data-background="img/brjs-homepage.png" data-background-size="100%" class="dark" -->

--

<!-- .slide: data-background="img/electronic-components.jpg" data-background-size="100%" data-state="black-bg alpha-bg" class="dark" -->

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

<!-- .slide: data-background="img/question-mark.jpg" data-background-size="100%" data-state="black-bg alpha-bg" class="dark" -->

## Why Build Components?

--

### Modular

* Separation of Concerns
* Encapsulation
* Information Hiding
* A defined interface/contract/API
* Improved maintenance

![](img/buzzword-bingo.jpg)

Note:

- Component -> Modular: magical properties
- Semantic overload again!
- Modules, components, widgets etc.
- Encapsulation: packing of data & functions into a single component
- Components ~= Modules

--

### High Cohesion

<blockquote>the degree to which the elements of a module belong together</blockquote>
<blockquote>a measure of how strongly related each piece of functionality expressed by the source code of a software module is</blockquote>
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

<!-- .slide: data-background="img/warning.png" data-background-size="100%" data-state="black-bg alpha-bg" class="dark" -->

### Don't over-engineer to achieve reusability

Note:

Don't focus too much on trying to build reusable components. Focus on building the required piece of functionality for your application, which may be very specific. Then, if the need arises, or it becomes very clear that the component is reusable, put in the extra effort to make the component reusable. As developers love to create reusable functionality (libraries, components, modules, plugins etc.). Doing so prematurely can result in a world of pain. So, take all the other benefits of component-based development and accept that not everything you write can be 100% reusable.

--

### Interchangable

* Same interface/contract
* Same functionality
* Swap easily

Note:

- focused component API presents the opportunity to be able to easily change the underlying implementation
- If loosely coupled you can actually completely swap one component for another
- service component that offered realtime functionality via GoInstant

--

#### Composable

![](img/gmail-components-composed.png)

Note:

- easy for one component to be composed of a number of other components
- component to stay focused
- reusing functionality already in other components
- More complex functionality can be built in this way
- Is `my-app` a component?

--

### Building Components Now

![](img/todomvc.png)

Note:

- Some libraries/frameworks provide in-build component support
- Demonstrate building components using most popular

--

## `my-avatar` Component Example

```html
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

![](img/webcomponents-logo.svg)

--

* Custom Elements
* Shadow DOM
* HTML Imports
* Templates

--

![](img/webcomponents-support-2014.png)

--

![](img/webcomponents-support-polyfills-2014.png)

--

### Platform.js

<a class="jsbin-embed" href="http://jsbin.com/pihuz/4/embed?html,output">JS Bin</a>

--

### X-Tag & Brick

<a class="jsbin-embed" href="http://jsbin.com/wexiz/2/embed?html,output">JS Bin</a>

Note:

- X-Tag - similar to Platform.js
- Brick - a set of components to build apps with

--

## Other Polyfills

* [bosonic](http://bosonic.github.io/)
* [W3C Custom Elements Polyfil](https://github.com/WebReflection/document-register-element#document-register-element)
* [X-Tag](https://github.com/x-tag/x-tag) <small>includes some other "core" components</small>

--

![](img/polymer.png)

--

### Polymer - Example

<a class="jsbin-embed" href="http://jsbin.com/gukoku/2/embed?html,output">JS Bin</a>

--

## Component Inter-Communication

##### ComponentX

```js
var ServiceRegistry = require( 'br/ServiceRegistry' )
var eventHub = ServiceRegistry.getService( 'br.event-hub' );
eventHub.channel( 'foo' ).trigger( 'bar', { some: 'data' } );
```
##### ComponentY

```js
var ServiceRegistry = require( 'br/ServiceRegistry' )
var eventHub = ServiceRegistry.getService( 'br.event-hub' );
eventHub.channel( 'foo' ).bind( 'bar', function( data ) {
  // handle event
}, this );
```

Note:

- "independent" and "modular" how do they communicate?
- directly reference each other and interact via their API?!
- loose coupling where components have little or no knowledge of each other
- Use services
- Angular and Ember use services & DI

--

## Conclusion

* Components = Benefits
* Existing libs/frameworks - Components
* Native Web Components = Future
* Existing libs/frameworks will align
* Build new libs/frameworks on new foundation


Note:

--

# Thanks!
# Questions?
<br />
#### Phil [@leggetter](http://www.leggetter.co.uk)
#### [BladeRunnerJS](http://bladerunnerjs.org)
<br />
#### [j.mp/componentised-web](http://j.mp/componentised-web)
#### [j.mp/componentised-web-blog](http://j.mp/componentised-web-blog)
