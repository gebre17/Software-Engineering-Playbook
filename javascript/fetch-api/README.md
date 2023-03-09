# Fetch API

The Fetch API provides a powerful, flexible, and modern interface for accessing and manipulating HTTP requests and responses.

## Making a GET Request
```javascript
fetch('https://api.example.com/items')
  .then(response => {
    if (!response.ok) {
      throw new Error(`HTTP error! status: ${response.status}`);
    }
    return response.json();
  })
  .then(data => console.log(data))
  .catch(error => console.error('Fetch error:', error));
```

## Making a POST Request
```javascript
async function createItem(name) {
  const response = await fetch('https://api.example.com/items', {
    method: 'POST',
    headers: {
      'Content-Type': 'application/json',
      'Authorization': 'Bearer YOUR_TOKEN'
    },
    body: JSON.stringify({ name: name })
  });
  
  if (!response.ok) {
    throw new Error('Failed to create item.');
  }
  
  return await response.json();
}
```

## CORS (Cross-Origin Resource Sharing)
*   A mechanism that uses additional HTTP headers to tell browsers to give a web application running at one origin access to selected resources from a different server.
*   *Fetch Mode:* `mode: 'cors'` (default) vs. `mode: 'no-cors'` (restricts reading response contents).
