# SecureStorage

**Usage**: `new SecureStorage()`  
**Description**: SecureStorage class is used to securely handle storage for a worker. It provides both session-specific and local storage.

**Returns** : SecureStorage instance.

```js
const secureStorage = new SecureStorage();
secureStorage.init();
```

## Public Properties

- store: An instance of `SubscribableStore` that provides an event-driven state container.

## Methods

### `init()`

**Usage**: `secureStorage.init()`
**Description**: Initializes the storage. It gets the current state from the local store, sets the initial state, and sets up a subscription to store changes.

**Returns** : Promise<void>. Does not return a value.

```js
secureStorage.init();
```

### `getWorkerState()`

**Usage**: `secureStorage.getWorkerState()`
**Description**: Gets the current worker state from the store.
**Returns** : Object representing the worker state.

```js
const workerState = secureStorage.getWorkerState();
```

### `getAppState()`

**Usage**: `secureStorage.getAppState()`
**Description**: Gets the current application state from the chrome storage.
**Returns** : Promise<Object>. Resolves with the object representing the application state.

```js
secureStorage.getAppState().then(appState => console.log(appState));
```

### `setAppState(state)`

**Usage**: `secureStorage.setAppState(state)`
**Description**: Sets the application state in the chrome storage.
Parameters:
- state: The state object to be set in the chrome storage.
  **Returns** : Promise<void>. Does not return a value.

```js
secureStorage.setAppState(newState).then(() => console.log('State set'));
```

### `setWorkerState(state)`

**Usage**: `secureStorage.setWorkerState(state)`
**Description**: Sets the worker state in the chrome storage.
Parameters:
- state: The state object to be set in the chrome storage.
  **Returns** : Promise<void>. Does not return a value.

```js
secureStorage.setWorkerState(newState).then(() => console.log('State set'));
```

### `clearAppState()`

**Usage**: `secureStorage.clearAppState()`
**Description**: Clears the application state in the store by setting it to the default state.
**Returns** : Promise<void>. Does not return a value.

```js
secureStorage.clearAppState().then(() => console.log('State cleared'));
```

## chromeStorage

**Description**: An object that provides helper functions to interact with the Chrome storage.

### `getWorkerState(isSession = false)`

**Description**: Gets the current worker state from Chrome storage.
Parameters:
- isSession: A boolean indicating whether to get the state from session storage (true) or local storage (false). Defaults to false.
  **Returns** : Promise<Object>. Resolves with the object representing the worker state.

### `getAppState(isSession = false)`

**Description**: Gets the current application state from Chrome storage.
Parameters:
- isSession: A boolean indicating whether to get the state from session storage (true) or local storage (false). Defaults to false.
  **Returns** : Promise<Object>. Resolves with the object representing the application state.

### `setWorkerState(object, isSession = false)`

**Description**: Sets the worker state in the Chrome storage.
Parameters:
- object: The state object to be set in the Chrome storage.
- isSession: A boolean indicating whether to set the state in session storage (true) or local storage (false). Defaults to false.
  **Returns** : Promise<void>. Does not return a value.

### `setAppState(object, isSession = false)`

**Description**: Sets the application state in the Chrome storage.
Parameters:
- object: The state object to be set in the Chrome storage.
- isSession: A boolean indicating whether to set the state in session storage (true) or local storage (false). Defaults to false.
  **Returns** : Promise<void>. Does not return a value.

### `clear(isSession = false)`

**Description**: Clears the Chrome storage.
Parameters:
- isSession: A boolean indicating whether to clear the session storage (true) or local storage (false). Defaults to false.
  **Returns** : Promise<boolean>. Resolves with true.
