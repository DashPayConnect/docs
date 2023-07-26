# SubscribableStore

Synchronous in-memory store that you can subscribe to.



**Usage**: `new SubscribableStore()`  
**Description**: Create an instance of SubscribableStore

Parameters: N/A

**Returns** : SubscribableStore instance.


```js
const store = new SubscribableStore();
// Subscribe to specific key//value
const handler = ({key, value}) => {
    console.log('handler called with value', value, 'for key', key);
};
store.subscribe(handler);  

// Subscribe to full store change
const handler = (state) => {
    console.log('handler called with state', state);
}  
store.subscribe(handler, true);  


// Put a key:value
store.put('key2', {bool:true, number: 42, squawk: 'squawk', obj: {a:1, b:2, c:3}});


// Get specific key
store.get('key2');

// Get full state
console.log(store.getState()); 
```
