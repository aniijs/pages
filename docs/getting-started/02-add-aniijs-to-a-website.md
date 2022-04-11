---
title: Add AniiJS to a Website
slug: /add-aniijs-to-a-website
---

In this section we will show you how to add AniiJS to your website.

<hr/>

## Without Babel

An example of how to add AniiJS to your website without using Babel is shown below.

:::info TIP

Using Babel is recommended for production use.

:::

### Step 1: Add the script tag

Add the `<script>` tags down below to the HTML page right before the closing `</head>` tag:

```html
	<!-- ... other HTML ... -->

	<!-- Load AniiJS. -->
	<script src="https://dist.aniijs.dev/latest/import.js" crossorigin></script>
	<!-- Add this line too, if you're not including AniiJS via "import" -->
	<script type="module" src="https://dist.aniijs.dev/latest/anii.js" crossorigin></script>

	<!-- Load your component. -->
	<script src="my_component.js"></script>
</head>
```

:::info INFO

You can change the component file name to whatever you want. In this case, we are using `my_component.js`.

:::

:::warning WARNING

This url will always load the latest version. If AniiJS get updates, it may break your code.<br/>
Use `https://dist.aniijs.dev/<id>/import.js` instead.

:::

### Step 2: Create a AniiJS Component

Next, create a file called `my_component.js` next to your `HTML` file.

```jsx title="my_component.js"
import {useToggle, createElement as create} from "anii";
export default function MyComponent() {
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

Copy the code above and paste it into the file you created.<br/>
After copying, add the following code to the bottom of the file:

```jsx
// --> The code you pasted <--

const domRoot = document.getElementById("root");
Anii.render(domRoot, create(MyComponent));
```

### Step 3: Add a DOM element which will be used as the root of your application

```html
<body>
	<!-- ... other HTML ... -->

	<div id="root"></div>

	<!-- ... other HTML ... -->
</body>
```

## With Babel (JSX Support)

The following examples will use Babel for JSX support.

### Quickly Try JSX

....

### External

An example of how to run AniiJS using Babel with external files is shown below.

:::caution CAUTION

This feature is still in early development. It may not work as expected. Please use it with caution.

:::

#### Step 1: ...

Step 1 desc

#### Step 2: ...

Step 2 desc

#### Step 3: ...

Step 3 desc

### Making a pre-compiled Application with Babel

An example of how to compile your AniiJS code with Babel is shown below.

#### Step 1: ...

Step 1 desc

#### Step 2: ...

Step 2 desc

#### Step 3: ...

Step 3 desc

## The end

Check out the next sections for more information on how to use AniiJS.

### Result

You have just created a simple AniiJS application. Well done!

<iframe id="codeFrame" src="/frame/add-aniijs-to-a-website-my_component.html"></iframe>
