## REST API

The REST API allows clients to interact with the LoopBack models using HTTP.
The clients can be a web browser, a JavaScript program, a mobile SDK, a curl
script, or anything that can act as an HTTP client.

LoopBack automatically binds a model to a list of HTTP endpoints that provide
REST APIs for model instance data manipulations (CRUD) and other remote
operations.

We'll use a simple model called `Location` (locations for rental) to illustrate
what REST APIs are exposed by LoopBack.

By default, the REST APIs are mounted to `/<pluralFormOfTheModelName>`, for
example, `/locations`, to the base URL such as http://localhost:3000/.

### CRUD remote methods

For a model backed by a data source that supports CRUD operations, you'll see
the following endpoints:

- Model.create: POST /locations
- Model.upsert: PUT /locations
- Model.exists: GET /locations/:id/exists
- Model.findById: GET /locations/:id
- Model.find: GET /locations
- Model.findOne: GET /locations/findOne
- Model.deleteById: DELETE /locations/:id
- Model.count: GET /locations/count
- Model.prototype.updateAttributes: PUT /locations/:id

### Custom remote methods

To expose a JavaScript method as REST API, we can simply describe the method as
follows:

    loopback.remoteMethod(
      Location.nearby,
      {
        description: 'Find nearby locations around the geo point',
        accepts: [
          {arg: 'here', type: 'GeoPoint', required: true, description: 'geo location (lat & lng)'},
          {arg: 'page', type: 'Number', description: 'number of pages (page size=10)'},
          {arg: 'max', type: 'Number', description: 'max distance in miles'}
        ],
        returns: {arg: 'locations', root: true},
        http: {verb: 'POST', path: '/nearby'}
      }
    );

The remoting is defined using the following properties:

- description: Description of the REST API
- accepts: An array of parameters, each parameter has a name, a type, and an
optional description
- returns: Description of the return value
- http: Binding to the HTTP endpoint, including the verb and path

### Request Format

For POST and PUT requests, the request body must be JSON, with the Content-Type
header set to application/json.

#### Encode the JSON object as query string

LoopBack uses the syntax from [node-querystring](https://github.com/visionmedia/node-querystring)
to encode JSON objects or arrays as query string. For example,

    user[name][first]=John&user[email]=callback@strongloop.com
    ==>
    { user: { name: { first: 'John' }, email: 'callback@strongloop.com' } }

    user[names][]=John&user[names][]=Mary&user[email]=callback@strongloop.com
    ==>
    { user: { names: ['John', 'Mary'], email: 'callback@strongloop.com' }}

    items=a&items=b
    ==> { items: ['a', 'b'] }

For more examples, please check out [node-querystring](https://github.com/visionmedia/node-querystring/blob/master/test/parse.js)


### Response Format

The response format for all requests is a JSON object or array if present. Some
responses have an empty body.

Whether a request succeeded is indicated by the HTTP status code. A 2xx status
code indicates success, whereas a 4xx status code indicates request related
issues. 5xx status code reports server side problems.

The response for an error is in the following format:

    {
    "error": {
        "message": "could not find a model with id 1",
        "stack": "Error: could not find a model with id 1\n ...",
        "statusCode": 404
        }
    }
