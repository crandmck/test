### App

Create a Loopback application.

```js
var loopback = require('loopback');
var app = loopback();

app.get('/', function(req, res){
  res.send('hello world');
});

app.listen(3000);
```
    
> **Notes**
>
> - extends [express](http://expressjs.com/api.html#express)
> - see [express docs](http://expressjs.com/api.html) for details
> - supports [express / connect middleware](http://expressjs.com/api.html#middleware) 

#### app.model(Model)

Expose a `Model` to remote clients.

```js
// create a testing data source
var memory = loopback.memory();
var Color = memory.createModel('color', {name: String});

app.model(Color);
app.use(loopback.rest());
```
    
> **Note** - this will expose all [shared methods](#shared-methods) on the model.
    
#### app.models()

Get the app's exposed models.

```js
var models = app.models();

models.forEach(function (Model) {
  console.log(Model.modelName); // color
});
```
    
#### app.docs(options)

Enable swagger REST api documentation.

**Options**

 - `basePath` The basepath for your API - eg. 'http://localhost:3000'.

**Example**

```js
// enable docs
app.docs({basePath: 'http://localhost:3000'});
```

Run your app then navigate to [the api explorer](http://petstore.swagger.wordnik.com/). Enter your API basepath to view your generated docs.
