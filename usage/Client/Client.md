# Client

**Usage**: `new Client()`  
**Description**: Hold the current account and a dashInstance client. Provides some helpers (sendMessage) and allow to switch accross account.

Parameters: N/A

**Returns** : Client instance.

```js
const client = new Client();
await client.connect()
const account = client.getCurrentAccount();
await client.disconnect()
```


## Public Properties 

- CHROME_ID: string
- state: ["IDLE", "CONNECTED", "DISCONNECTED"]
- currentAccount : Account
- dashInstance: Dash.Client instance (contains dashcore lib primitives, access to L1/L2 and wallet-lib).

## Methods

### `connect()`

**Usage**: `client.connect()`
**Description**: Connect to the extension and get the current account.
Parameters: N/A
**Returns** : Promise<Account>

### `disconnect()`

**Usage**: `client.disconnect()`
**Description**: Disconnect from the extension.
Parameters: N/A
**Returns** : Promise<void>

### `getCurrentAccount()`

**Usage**: `client.getCurrentAccount()`
**Description**: Get the current account as known at the last fetch performed by the client (on connect or on switchAccount by default).
Parameters: N/A

**Returns** : Account

### `fetchCurrentAccount()`

**Usage**: `client.fetchCurrentAccount()`
**Description**: Fetch the current account from the extension.
Parameters: N/A

**Returns** : Promise<Account>

### `isConnected()`

**Usage**: `client.isConnected()`
**Description**: Check if the client is connected to the extension.
Parameters: N/A

**Returns** : boolean

### `sendMessage(message)`

**Usage**: `client.sendMessage(message)`
**Description**: Send a message to the extension.
Parameters: message: Message

**Returns** : Promise<any>

### `switchCurrentAccount(walletId, accountIndex)`

**Usage**: `client.switchCurrentAccount(walletId, accountIndex)`
**Description**: Switch the current account to the one specified by the walletId and accountIndex.
Parameters: walletId: string, accountIndex: number

**Returns** : Promise<Account>

### `requestTransaction(opts)`

**Usage**: `client.requestTransaction(opts)`
**Description**: Request a transaction to the extension.
Parameters: opts: TransactionOpts

**Returns** : Promise<Transaction>






