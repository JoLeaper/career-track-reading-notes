# Class 07 Reading

## Express Routing:
```js
app.(get/post/patch/etc.)('/thing', (req, res) => {}
})

// req === request
// res === response
```
This code snippet waits to hear for an event that happens on '/thing,' then runs the function using the request and response as parameters.

### Request:
- (req)
```js
app.get('/api/:thing', ...) = req.params.thing
// thing would be equal to whatever is in place of :thing.
```
When making a request, :thing would be a params (or parameter).

```js
app.get('/api?ball=round') = req.query.ball

// A question mark in a request is linked to a query. Think key:value pair. In this case, req.query.ball is looking at queries in the request with they key of 'ball.' Therefore, req.query.ball is round.
```

### Response:
- (..., res)
- the response, responsible for sending data back to the browser.
- send/status are methods attached that Express uses to format the output. 
- Send headers, cookies, status codes, authorization, etc.

# Express Middleware
- Middleware is a series of functions that the request has to go through.
- Each function gets a request, response, and next as parameters.
- Types include Application and Route.
- Others include:
- - Error Handling
- - Bringing in other routes.
- - Applies defaults.
- - JSON parsing
- - Runs on every request.
## Route Middleware
- Deals with specific things for a route.
- Checks for if you're logged in, IP address, whether you regularly visit the site.

## Used With:
- Logging
- Dynamic Model Loading
- Browser, Location, user specific content
- consistent data transition/modeling/prep

## Makes Modular Code

# CRUD OPERATIONS
-CREATE
```js
app.post('/resource')
```
-READ
```js
app.get('/resource')
```
-UPDATE
```js
app.put('/resource/:id')
```
-DESTROY
```js
app.get('/resource/:id')
```

## Server Testing
- Avoid starting the server for testing.
- Instead, export server as a library.
- Then use supertest to run tests.