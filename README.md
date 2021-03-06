# Node-Snippets
Snippets or patterns of useful Node code

## Snippets
- [events](#events)

### Events
#### Implementation
```javascript
// dispatch.js
// Simple API for Event dispatching in Node
var EventEmitter = require('events');
var observer = new EventEmitter();

module.exports = {
	// Register listener for an event
	on: function(event, callback) {
		observer.on(event, callback);
	},
	// Emit an event
	emit: function(event, arg) {
		observer.emit(event, arg);
	}
}
```
#### Use
```javascript
var dispatch = require('./dispatch');

dispatch.on('eventMessage', function(event) {
	console.log('Heard an event');
	if (event) console.log(event.title);
});

dispatch.emit('eventMessage', {title: 'this is super jazz!'});
```
