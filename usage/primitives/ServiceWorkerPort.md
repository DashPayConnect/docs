# ServiceWorkerPort

**Usage**: `new ServiceWorkerPort()`  
**Description**: `ServiceWorkerPort` is a class for establishing and handling communication between a service worker and another part of the system (typically an extension) through a messaging port.

**Returns** : An instance of ServiceWorkerPort.

```js
const ServiceWorkerPort = require('<path to file>');
const serviceWorkerPort = new ServiceWorkerPort();
```

## Public Properties

- editorExtensionId: The id of the extension the service worker will connect to.
- port: The communication port between the service worker and the extension.

## Methods

### `connect(editorExtensionId)`

**Usage**: `serviceWorkerPort.connect(editorExtensionId)`  
**Description**: Connects to an extension by opening a long-lived connection port between the service worker and the extension with the provided id.

Parameters:
- editorExtensionId: The id of the extension to connect to.

**Returns**: The connection port.

```js
serviceWorkerPort.connect('extensionId');
```

### `postMessage(msg)`

**Usage**: `serviceWorkerPort.postMessage(msg)`  
**Description**: Posts a message through the port to the other end of the connection.

Parameters:
- msg: The message to be sent.

```js
serviceWorkerPort.postMessage('Hello');
```

### `handleMessage(msg)`

**Usage**: `serviceWorkerPort.handleMessage(msg)`  
**Description**: Handles a received message from the other end of the port.

Parameters:
- msg: The received message.

```js
serviceWorkerPort.handleMessage(msg);
```

## Events

### `onMessage.addListener((message)=>{})`

**Usage**: Inside `connect()` method  
**Description**: Listens for messages from the other end of the port. When a message is received, it is passed to the `handleMessage` function.

```js
port.onMessage.addListener((message) => this.handleMessage.call(this, message));
```
