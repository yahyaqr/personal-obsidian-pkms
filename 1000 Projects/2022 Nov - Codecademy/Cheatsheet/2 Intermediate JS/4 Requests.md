---
created: Sunday, October 30th 2022 - 01.35
updated: Sunday, October 30th 2022 - 01.35
---
### JSON-Formatted Response body
The `.json()` method will resolve a returned promise to a JSON object, parsing the body text as JSON.

In the example code, the `.json()` method is used on the `response` object which returns a promise to a JSON-formatted response body as `jsonResponse`.
```js
fetch('url')
.then((response) => response.json())
.then((jsonResponse) => {console.log(jsonResponse);
});
```

### The fetch() Function
```js
fetch('url')
.then(
	response  => {
	    console.log(response);
  },
	rejection => {
		console.error(rejection.message);
);
```

### Using async...await with Fetch
```js
const getSuggestions = async () => {
  const wordQuery = inputField.value;
  const endpoint = `${url}${queryParams}${wordQuery}`;
  
  try {
	const response = await fetch(endpoint, {cache: 'no-cache'});
    if (response.ok) {
      const jsonResponse = await response.json()
    }
  } catch (error) {
    console.log(error)
  }
}
```