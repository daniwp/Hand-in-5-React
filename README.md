# Hand-in 5, Single Page Applications with React

>## Describe the term Single Page Application (SPA) and why it’s relevant for modern web-applications.
#### SPA Term:
A single-page application (SPA) is a web application or web site that fits on a single web page with the goal of providing a user experience similar to that of a desktop application. In an SPA, either all necessary code – HTML, JavaScript, and CSS – is retrieved with a single page load, or the appropriate resources are dynamically loaded and added to the page as necessary, usually in response to user actions. The page does not reload at any point in the process, nor does control transfer to another page, although the location hash or the HTML5 History API can be used to provide the perception and navigability of separate logical pages in the application. Interaction with the single page application often involves dynamic communication with the web server behind the scenes.

#### SPA Relevance:
- SPA is fast, as most resources (HTML+CSS+Scripts) are only loaded once throughout the lifespan of application. Only data is transmitted back and forth.

- The development is simplified and streamlined. There is no need to write code to render pages on the server. It is much easier to get started because you can usually kick off development from a file http://file://URI, without using any server at all.

- SPAs are easy to debug with Chrome, as you can monitor network operations, investigate page elements and data associated with it.

- It’s easier to make a mobile application because the developer can reuse the same backend code for web application and native mobile application.

- SPA can cache any local storage effectively. An application sends only one request, store all data, then it can use this data and works even offline.

A major architectural advantage of a SPA in many cases is the huge reduction in the "chattiness" of your app. If you design it properly to handle most processing on the client (the whole point, after all), then the number of requests to the server is dramatically reduced. In fact, a SPA makes it possible to do entirely offline processing, which is huge in some situations.

Performance is certainly better with client-side rendering if you do it right, but this is not the most compelling reason to build a SPA. (Network speeds are improving, after all.) Don't make the case for SPA on this basis alone.

Flexibility in your UI design is perhaps the other major advantage.
---
>## Describe fundamental differences between the SPA-framework/libraries AngularJS and React
### AngularJS vs React
The main differences between AngularJS (the framework) and React (the library) are in the following aspects: componentization, data binding, performance, dependency resolution, directives, and templating.

### Componentization
#### AngularJS
AngularJS has a very complex and fixed structure because it's based on the three layers — Model, View, and Controller — typical of single-page applications. An object $scope in AngularJS is responsible for the Model part, which is initialized by the Controller and then transformed into HTML to create the View for the user. AngularJS provides many standard services, factories, controllers, directives, and other components that will take some time for a JavaScript developer to master initially.

#### React
Facebook, the creator of React, chose an architecture different from that of AngularJS and similar MVC frameworks. In short, there is no “correct" structure for applications built with React.

React is a large JavaScript library that helps us update the View for the user. But React still doesn't let us create applications on its own. The library lacks the model and controller layers. To fill in the gap, Facebook introduced Flux, which has numerous variants nowadays, to control the application workflow.

React provides a very simple and efficient way to build component trees. It boasts a functional programming style where component definitions are declarative. Composing your app from React components is like composing a JavaScript program from functions.

### Data Binding
#### AngularJS
AngularJS connects Document Object Model (DOM) values to Model data through the Controller using two-way data binding. In short, if the user interacts with an <input> field and provides a new value to the app, then not only the View is updated, but the Model as well. Two-way data binding is beneficial for AngularJS as it helps us write less boilerplate code to create interactions between components (the View and the Model) in our application. We don't have to invent a method to track changes in the app and change our JavaScript code accordingly.

The drawback of Angular's two-way data binding approach is its negative impact on performance. AngularJS automatically creates a watcher for each binding. During development, we may come to a point when an app is packed with too many watchers for bound elements.

#### React
But what are the advantages of React over AngularJS with regards to data binding? React uses one-way data binding, meaning we are able to direct the flow of data only in one direction. Because of this, it’s always clear where the data was changed.

![alt text](https://rubygarage.org/uploads/article_image/file/122/reactjs-vs-angularjs-data-flow.jpg)

In order to implement a unidirectional data flow in React, Facebook created its own application architecture called Flux. Flux controls the flow of data to React components through one control point – the dispatcher. Flux's dispatcher receives an object (they call it an action) and transfers it to an appropriate store, which then updates itself. Once the update is finished, the View changes accordingly and sends a new action to the dispatcher. It's only possible to transfer an action to the store when it’s fully updated. With this concept, Flux improves the effectiveness of the code base. Based on our own experience we can say that Flux is great when you work with dynamically updated data.

The one-way data flow in React keeps complexity under control. It's much easier to debug self-contained components of large React applications than it is with similarly large AngularJS applications.

### Performance
#### AngularJS
There are two things to take into consideration when we talk about Angular's performance. Angular 1.x and higher relies on two-way data binding. This concept is based on “dirty checking," a mechanism that can make our AngularJS application laggy.

When we bind values in HTML with our model, AngularJS creates a watcher for each binding to track changes in the DOM. Once the View updates (becomes “dirty"), AngularJS compares the new value with the initial (bound) value and runs the $digest loop. The $digest loop then checks not only values that have actually changed, but also all others values that are tracked through watchers. This is why performance will decrease a lot if your application has too many watchers. This drawback is even more painful when several values (Views) are dependent on each other. Once AngularJS sees that the change of a value was triggered by another change of a different value, then it stops the current $digest cycle and runs it all over again.

#### React
The creators of React introduced the concept of the virtual Document Object Model, which is regarded as one of the greatest advantages of React in comparison with mature frameworks, including AngularJS. How does the virtual DOM work? When our HTML document is loaded, React creates a lightweight DOM tree from JavaScript objects and saves it on the server. When the user, for instance, enters new data in the <input> field in the browser, React creates a new virtual DOM and then compares it with the previously saved DOM. The library finds dissimilarities between two object models in such a way and rebuilds the virtual DOM once again, but with new changed HTML. All this work is done on the server, which reduces load on the browser.

Now, instead of sending completely new HTML to the browser, React sends the HTML only for the changed element. This approach is much more efficient than what AngularJS offers.

### Resolving Dependencies
#### AngularJS

#### React


### Directives and Templates
#### AngularJS

#### React


>## Describe the overall principles used in React to create a SPA

>## Explain, using an example, the fundamental building blocks in React Applications like:
* JSX
* Rendering Elements
* Components and Props
* State and LifeCycle
* Handling Events
* List and Keys
* Working with Forms
* Lifting State Up

>## Describe tools like Babel, WebPack and create-react-app and how they fit in to the React-world

>## Explain, using examples, about Class Components, versus pure JavaScript functions in React, and when to use them.

>## Explain the purpose of Client Side Routing in a SPA

>## Explain, using an example of your own, the basic “building blocks” in react-router

>## Explain what is required to use react-router with a create-react-app project build from scratch

>## Explain, using examples, how JavaScript array methods, like filter, map and (reduce) are used to generate dynamic HTML structures (tables, ul's etc.), and explain about React Keys.
