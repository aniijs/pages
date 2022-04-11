---
title: Introduction
slug: /
---

:::warning WARNING

This library is a work in progress. Anything can change **at any moment** without any notice!

:::

<hr />

## What is AniiJS? And Why Should I Use It?

AniiJS is a JavaScript library for building user interfaces. And provides declarative and component-based programming model that can help you to save time.<br/>
AniiJS features [ReactJS](https://reactjs.org/) like syntax, so if you're a ReactJS developer, you can get used to AniiJS fast and easily.<br/><br/>
You should definitely use it if you're wanting to build your own user interface without getting into the details of the HTML & CSS & JavaScript.<br/>
Also, It's a good way to learn the basics of front-end development and to get familiar with the JavaScript programming language.

## Basic Example

```jsx title="bookmark.js"
import {useToggle, createElement as create} from "anii";
export default function Bookmark() {
	const [bookmark, setBookmark] = useToggle(false);
	if (bookmark) {
		return create("p", null, "Already bookmarked!");
	}
	return create(
		"button",
		{
			onClick: () => setBookmark(true),
		},
		"Bookmark!"
	);
}
```

### Result of the Basic Example

<iframe id="codeFrame" src="/frame/introduction-bookmark.html"></iframe>
<br />
The above example is a basic example of AniiJS. You can see the result of the example changes by clicking the "Bookmark!" button.

## JSX&Hooks Example

```jsx title="todo.js"
import {useState, useRef} from "anii";

export default function Todo() {
	const todoInput = useRef();
	const [todos, setTodos] = useState([]);

	const addTodo = (todo) => {
		if (todo.replaceAll(" ", "") == "") return;
		setTodos([...todos, todo]);
	};

	return (
		<div>
			<h1>Todo List</h1>
			<input type="text" ref={todoInput} placeholder="Todo" />
			<button onClick={() => addTodo(todoInput.current.value)}>Add</button>
			<ul style={{padding: "5px 0px 0px 0px", textAlign: "center", listStyle: "none"}}>
				{todos.map((todo) => (
					<li>{todo}</li>
				))}
			</ul>
		</div>
	);
}
```

### Result of the JSX&Hooks Example

<iframe id="codeFrame" src="/frame/introduction-todo.html"></iframe>

<br />
The above example is a simple todo list. You can add a new todo by typing it in the input box and clicking the "Add" button.<br />

## I don't understand the examples above!??!!!

You may already have questions about the code above. Don't worry, we will explain every little detail in the next sections.
