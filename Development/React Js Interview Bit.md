# What is React 
1.  useful in developing user interfaces specifically for ==applications with a single page==
2.  building ==complex and reusable user interface(UI)== components of mobile and web applications
### IMP FEATURES :
- It supports **server-side rendering**.
- It will make use of the **virtual DOM** rather than real DOM (Data Object Model) as RealDOM manipulations are expensive.
- It follows ==unidirectional data binding or data flow==.
- It uses reusable or composable UI components for developing the view.
# Advantages of React:
#### In short : 
**Use of Virtual DOM to improve efficiency**
**Gentle learning curve:**
**SEO friendly**
**Reusable components:**
**Huge ecosystem of libraries to choose from:**

If you want to have in Depth Each point : https://chatgpt.com/share/66f5a3c5-cea0-800a-a02f-6f05a1cba28b gpt Link 

# What are the limitations of React?

The few limitations of React are as given below:
- React is not a full-blown framework as it is only a library.
- The components of React are numerous and will take time to fully grasp the benefits of all.
- It might be difficult for beginner programmers to understand React.
- Coding might become complex as it will make use of inline templating and JSX.
# What is useState() in React?

- The useState() is a built-in React Hook
- allows you for having state variables in functional components.
-  DOM has something that is dynamically manipulating/controlling

![[Pasted image 20240926234930.png]]

- setCounter method will allow us to update the state of the counter.
- first parameter that represents the counter’s current state
- We can make use of setCounter() method for updating the state of count anywhere
#  What are keys in React?
- special string attribute that needs to be included when using lists of elements.
Sniipt : 
![[Pasted image 20240926235847.png]]

**Importance of keys -**
- Keys help react identify which elements were added, changed or removed.
- Keys should be given to array elements for providing a unique identity for each element.
- Without keys, React does not understand the order or uniqueness of each element.
- With keys, React has an idea of which particular element was deleted, edited, and added.
- Keys are generally used for displaying a list of data coming from an API.
# What is JSX?
- JSX stands for JavaScript XML.
- allows us to write HTML inside JavaScript and place them in the DOM without using functions like appendChild( ) or createElement( )

    Note- We can create react applications without using JSX as well.

![[Pasted image 20240927004602.png]]

# What are the differences between functional and class components?
 -  functional components were called stateless components before the intro of hooks 
 - After the introduction of Hooks, functional components are equivalent to class components.
 
 -- **The Implementation Part of the both components one is a fn and other is a class of js** 
 ![[Pasted image 20240927010831.png]]

all type of Implmentation you can read it on the interviewbit i am giving the link : https://www.interviewbit.com/react-interview-questions/#functional-vs-class-components

# What is the virtual DOM? How does react use the virtual DOM to render the UI?
- As stated by the react team, virtual DOM is a concept where a virtual representation of the real DOM is kept inside the memory and is synced with the real DOM by a library such as ReactDOM.
- For every DOM object, there is a corresponding virtual DOM object(copy),
- The main difference between the real DOM object and the virtual DOM object is that any changes in the virtual DOM object will not reflect on the screen directly
- virtual DOM object as a blueprint
- React uses two virtual DOMs to render the user interface. One of them is used to store the current state of the objects and the other to store the previous state of the objects
- Whenever the virtual DOM gets updated, react compares the two virtual DOMs and gets to know about which virtual DOM objects were updatedAfter knowing which objects were updated, react renders only those objects inside the real DOM instead of rendering the complete real DOM.
##### **Why was virtual DOM introduced?**
###### Limitation of DOM: 
 Dom is important but DOM manipulation is quite slow when compared to other operations in JavaScript
 Most JavaScript frameworks update the entire DOM even when a small part of the DOM changes.
 application gets affected when several DOM manipulations are being done

# What are the differences between controlled and uncontrolled components?
are just different approaches to handling input from elements in react
##### **Controlled component:**
- In a controlled component, the value of the input element is controlled by React
- store the state of the input element inside the code, and by using event-based callbacks
- any changes made to the input element will be reflected in the code as well
- When a user enters data inside the input element of a controlled component, onChange function gets triggered and inside the code, we check whether the value entered is valid or invalid. If the value is valid, we change the state and re-render the input element with the new value.
-  Code![[Pasted image 20240927014311.png]]
##### Uncontrolled component:
- the value of the input element is handled by the DOM itself
- input elements inside uncontrolled components work just like normal HTML input form elements
- The state of the input element is handled by the DOM
- event-based callbacks are not called. Basically, react does not perform any action when there are changes made to the input element.
- Whenever use enters data inside the input field, the updated data is shown directly. To access the value of the input element, we can use **ref**.
- ![[Pasted image 20240927015810.png]]
# What are props in React?
inputs to a component of React

![[Pasted image 20240927020142.png]]
# Explain React state and props.
#### React State : 
Every component in react has a built-in state object, which contains all the property values that belong to that component.
Any change in the property values of the state object leads to the re-rendering of the component.
  *State object is not available in functional components but, we can use React Hooks to add state to a functional component.*
  