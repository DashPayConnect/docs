# WorkDispatcher

**Usage**: `new WorkDispatcher(dashManager, storage)`  
**Description**: WorkDispatcher class is used to handle and dispatch received messages across the service worker. It works with a Dash Manager and a storage instance.

**Returns** : WorkDispatcher instance.

```js
const WorkDispatcher = require('<path to file>');
const workDispatcher = new WorkDispatcher(dashManager, storage);
```

## Public Properties

- dashManager: DashManager instance used to manage dash functionalities.
- storage: An instance of SecureStorage to handle storage.

## Methods

### `create(request)`

**Usage**: `workDispatcher.create(request)`  
**Description**: This function creates new resources based on the request. It supports the creation of a new wallet from a mnemonic.

Parameters:
- request: The request object containing the arguments for creation.

**Returns** : Promise<void>. Does not return a value.

```js
workDispatcher.create(request);
```

### `connect(request)`

**Usage**: `workDispatcher.connect(request)`  
**Description**: Connects the request with the current account in the dash manager.

Parameters:
- request: The request object.

**Returns** : Promise<request>. Resolves with the request object.

```js
workDispatcher.connect(request);
```

### `fetch(request)`

**Usage**: `workDispatcher.fetch(request)`  
**Description**: Fetches resources based on the request type. It supports fetching accounts, addresses, balance, and transaction history.

Parameters:
- request: The request object containing the arguments for fetching.

**Returns** : Promise<request>. Resolves with the request object.

```js
workDispatcher.fetch(request);
```

### `generate(request)`

**Usage**: `workDispatcher.generate(request)`  
**Description**: Generates new resources based on the request. It supports the generation of a new mnemonic.

Parameters:
- request: The request object containing the arguments for generation.

**Returns** : request. Returns the request object.

```js
workDispatcher.generate(request);
```

### `update(request)`

**Usage**: `workDispatcher.update(request)`  
**Description**: Updates resources based on the request. It supports updating the network and offline mode of an account instance.

Parameters:
- request: The request object containing the arguments for updating.

**Returns** : Promise<request>. Resolves with the request object.

```js
workDispatcher.update(request);
```

### `execute(request)`

**Usage**: `workDispatcher.execute(request)`  
**Description**: Executes tasks based on the request. It supports executing transactions, switching accounts, and converting mnemonics to wallet IDs.

Parameters:
- request: The request object containing the arguments for execution.

**Returns** : Promise<request>. Resolves with the request object.

```js
workDispatcher.execute(request);
```

Please note that you need to understand how DashManager works and what type of storage instance you're providing to use this class properly.
