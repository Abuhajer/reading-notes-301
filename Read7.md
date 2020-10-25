# SuperAgent

SuperAgent is light-weight progressive ajax API crafted for flexibility, readability, and a low learning curve after being frustrated with many of the existing request APIs. It also works with Node.js!

 `request`
   `.post('/api/pet')`
   `.send({ name: 'Manny', species: 'cat' })`
   `.set('X-API-Key', 'foobar')`
   `.set('Accept', 'application/json')`
   `.then(res => {`
    `  alert('yay got ' + JSON.stringify(res.body));`
   `}); request`
   `.post('/api/pet')`
   `.send({ name: 'Manny', species: 'cat' })`
   `.set('X-API-Key', 'foobar')`
   `.set('Accept', 'application/json')`
   `.then(res => {`
    `  alert('yay got ' + JSON.stringify(res.body));`
   `});`

   # Test documentation

   The following test documentation was generated with Mocha's "doc" reporter, and directly reflects the test suite. This provides an additional source of documentation.

   # Request basics

   A request can be initiated by invoking the appropriate method on the request object, then calling `.then()` (or `.end()` or await) to send the request. For example a simple GET request:

   `request`
   `.get('/search')`
   `.then(res => {`
      `// res.body, res.headers, res.status`
   `})`
   `.catch(err => {`
    `  // err.message, err.response`
   `});`

   HTTP method may also be passed as a string:

   `request('GET', '/search').then(success, failure);`

   Old-style callbacks are also supported, but not recommended. Instead of `.then()` you can call `.end():Old-style` callbacks are also supported, but not recommended. Instead of `.then()` you can call `.end()`:

   `request('GET', '/search').end(function(err, res){`
  `if (res.ok) {}`
`});request('GET', '/search').end(function(err, res){`
 ` if (res.ok) {}`
`});`

