# DashManager

Used to work with multiple Dash's instance.

**Usage**: `new DashManager(storage)`  
**Description**: Create an instance of DashManager.

Parameters: 
- storage: Storage Instance.

**Returns** : DashManager instance.


```js
const DashManager = require('path_to_DashManager');
const storage = {}; // Assume this is your storage object
const manager = new DashManager(storage);
```

## Public Properties

- instances: Object holding all Dash instances.
- storage: Instance of the storage provided during construction.

## Methods

### `init()`

**Usage**: `manager.init()`
**Description**: Initialize the DashManager. Retrieves the app state from storage, and if it finds a current account with a mnemonic wallet type, it creates an instance with the current account's mnemonic and index.
Parameters: N/A
**Returns** : Promise<void>

### `getInstance(walletId)`

**Usage**: `manager.getInstance(walletId)`
**Description**: Retrieves a Dash instance from the manager.
Parameters: walletId: string
**Returns** : Dash.Client instance

### `switchAccountInstance(walletId, accountIndex)`

**Usage**: `manager.switchAccountInstance(walletId, accountIndex)`
**Description**: Switch the current account in the specified Dash instance to the account specified by the accountIndex.
Parameters: walletId: string, accountIndex: number
**Returns** : Promise<Dash.Client instance>

### `changeAccountInstanceNetwork(walletId, accountIndex, network, offlineMode)`

**Usage**: `manager.changeAccountInstanceNetwork(walletId, accountIndex, network, offlineMode)`
**Description**: Changes the network of the specified Dash instance and account.
Parameters: walletId: string, accountIndex: number, network: string, offlineMode: boolean
**Returns** : Promise<void>

### `createInstance(walletOpts, clientOpts)`

**Usage**: `manager.createInstance(walletOpts, clientOpts)`
**Description**: Creates a new Dash instance with the given wallet and client options, and switches to the account specified in the wallet options.
Parameters: walletOpts: Object, clientOpts: Object
**Returns** : Promise<Dash.Client instance>

### `computeWalletIdFromMnemonic(mnemonic)`

**Usage**: `manager.computeWalletIdFromMnemonic(mnemonic)`
**Description**: Computes a wallet ID from a given mnemonic.
Parameters: mnemonic: string
**Returns** : string

### `generateMnemonic()`

**Usage**: `manager.generateMnemonic()`
**Description**: Generates a new mnemonic and computes the walletId from this mnemonic.
Parameters: N/A
**Returns** : Object containing the generated mnemonic string

```js
const mnemonicData = manager.generateMnemonic();
console.log(mnemonicData); // Outputs: {mnemonic: <mnemonic>}
```
This method generates a mnemonic phrase which is used for cryptographic security and key generation. It then returns an object with the newly created mnemonic.
The generated mnemonic could then be used in the `computeWalletIdFromMnemonic()` function to obtain the wallet id.
