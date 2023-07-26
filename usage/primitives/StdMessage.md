# StdMessage

**Usage**: `new StdMessage(action, args, sender)`  
**Description**: StdMessage is a class for creating standard messages in a system, typically used for communication between different parts of a system (e.g., server to client, client to server).

**Returns** : StdMessage instance.

```js
const StdMessage = require('<path to file>');
const message = new StdMessage(action, args, sender);
```

## Public Properties

- action: Specifies the type of action to be performed.
- args: Array of arguments related to the action.
- sender: The sender of the message.

## Static Properties

- ACTIONS: An object defining the set of possible actions that a StdMessage can represent.

## Static Methods

### `fromMessage(message, sender)`

**Usage**: `StdMessage.fromMessage(message, sender)`  
**Description**: This static method is used to create a new StdMessage from a given message object and a sender.

Parameters:
- message: The message object from which to create the StdMessage.
- sender: The sender of the message. If not provided, it will use the sender from the message object.

**Returns** : StdMessage instance.

```js
let msg = StdMessage.fromMessage(message, sender);
```

## Methods

### `getTabId()`

**Usage**: `message.getTabId()`  
**Description**: Gets the ID of the sender's tab if it exists.

**Returns** : Tab id if it exists or false.

```js
let tabId = message.getTabId();
```

### `toJSON()`

**Usage**: `message.toJSON()`  
**Description**: Converts the StdMessage instance to a JSON object containing the action, args, and sender properties.

**Returns** : JSON object.

```js
let jsonObject = message.toJSON();
```

## Defined Actions

- PING
- PONG
- CREATE
- EXECUTE
- GENERATE
- FETCH
- CONNECT
- UPDATE
- CLOSE
- DISCONNECT
- UNDEFINED_ACTION

Note: The list of defined actions may vary depending on the context of usage. In a different context, the actions might be different.
