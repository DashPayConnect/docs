```
# MessageHandler

**Usage**: `new MessageHandler(workDispatcher)`  
**Description**: Handles incoming messages, classifies them into the required action, and routes them to the corresponding function in `workDispatcher`. 

Parameters: workDispatcher: Object responsible for the actual execution of the classified action.

**Returns** : MessageHandler instance.

```js
const messageHandler = new MessageHandler(workDispatcher);
messageHandler.setListeners();
```

## Public Properties

- workDispatcher: The object that performs the action defined by the message.

## Methods

### `setListeners()`

**Usage**: `messageHandler.setListeners()`
**Description**: Set the message listeners for Chrome runtime.
Parameters: N/A

**Returns** : N/A

```js
messageHandler.setListeners();
```

### `handleMessage(message, sender, sendResponse)`

**Usage**: `messageHandler.handleMessage(message, sender, sendResponse)`
**Description**: Handles a received message. It transforms the raw message into a standard format (StdMessage), classifies it according to the action defined in the message, and then routes it to the corresponding function in `workDispatcher`. It sends the response received from the workDispatcher back to the sender.
Parameters:
- message: The message received
- sender: The sender of the message
- sendResponse: The function used to send a response back to the sender

**Returns** : boolean. Always returns `true`.

```js
messageHandler.handleMessage(message, sender, sendResponse);
```
