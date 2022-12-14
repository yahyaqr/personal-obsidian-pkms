Variable Attributes in JSX

When writing JSX, it’s common to use variables to set _attributes_.

Here’s an example of how that might work:

```JSX
// Use a variable to set the `height` and `width` attributes:
const sideLength = "200px";
const panda = (
	<img
		src="images/panda.jpg"
		alt="panda"
		height={sideLength}
		width={sideLength}
	/>
);
```

Notice how in this example, the `<img />`‘s attributes each get their own line. This can make your code more readable if you have a lot of attributes on one element.

_Object properties_ are also often used to set attributes:

```JSX
const pics = {
	panda: "http://bit.ly/1Tqltv5",
	owl: "http://bit.ly/1XGtkM3",
	owlCat: "http://bit.ly/1Upbczi"
};
	
const panda = (
	<img
		src={pics.panda}
		alt="Lazy Panda"
	/>
);

const owl = (
	<img
		src={pics.owl}
		alt="Unimpressed Owl"
	/>
);
		
const owlCat = (
	<img
		src={pics.owlCat}
		alt="Ghastly Abomination"
	/>
); 
```