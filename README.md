# Angular Backbone Models

Backbone-style models for Angular. If you're like me, one of the things you miss the most switching
to Angular is the lack of clearly defined models and collections which you can pass around, attach
custom methods too, call fetch on to update new data, etc. I didn't find anything that fit my needs
so I built a very simple, rough implementation that I hopefully expand upon.

### How to use
- Add a script tag for underscore.js (http://underscorejs.org/) and angular-backbone-models.js
- Add 'abModels' as a dependency of your app or module:
````
angular.module( 'myApp', ['abModels']);
````
- Inject 'Model' or 'Collection' and extend it just you would a backbone model giving it a 'urlRoot'
for the model or 'url' for the collection just as in Backbone. See backbone (http://backbonejs.org)
for more info:
````
.factory('MyModel', function(Model){
  return Model.extend({
	urlRoot: '/api/mymodel'
  });
````
- Now make an instance of the model and call .fetch(), .save(), .toJSON() or other methods as with Backbone.
````
var model = new MyModel({ id: 400 });
model.fetch();
model.set({ name: 'test' });
model.save();
console.log(model.toJSON());
````

### To do:
- achieve better parity and consistency with how Backbone methods, arguments, etc.
- add tests
- remove dependency on underscore
- clean up
- better docs and instructions
- convert tabs to spaces