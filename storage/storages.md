## Storages

The extension provides a persistent storage for the data.  
It relies on WebStorage API, which is available in all modern browsers.  
Session storage is being used for the data that needs to be kept for the duration of the session, especially when sensible.  
The localStorage maintains a persistance accross sessions.  


Internally, we separate between app data and worker data (see more information on data flow). 

### App data

The app data is stored in the localStorage.  

### Worker data

The worker data is stored in the local storage.


## Extension storage 

### storage.js
This file is a utility module for interacting with the Chrome Extension Storage API. It exports various helper functions for getting and setting data.

Here are the exported functions:

- getStorageData(): This function fetches all the data currently stored in Chrome's sync storage.
- setStorageData(data): This function takes a JavaScript object and stores it in Chrome's sync storage.
- getStorageItem(key): This function takes a key and fetches the corresponding value from Chrome's sync storage.
- setStorageItem(key, value): This function takes a key-value pair and stores it in Chrome's sync storage.
- initializeStorageWithDefaults(defaults): This function initializes Chrome's sync storage with a default set of data if it hasn't been already.

### stores/stores.js
This file uses the Svelte store to manage state in a Svelte application. It creates an AppStore which holds various application states and provides methods to update these states. It also creates multiple derived stores to access different parts of the state.

Here are the key parts of AppStore:

- changePage(pageInfoObj): Changes the current page of the app.
- changeCurrentAccount(accountIndex): Changes the current account.
- changeCurrentWallet(walletId): Changes the current wallet.
- fullReset(): Resets the app store to its default state.
- importWallet(walletInfoObj), importAccount(accountInfoObj), importContact(contactInfoObj): Import wallet, account or contact info respectively into the app store.
- setFiatCurrency(value), setI18nValue(value), setNetwork(value), setOfflineMode(value): Update various settings in the app store.
- 
Furthermore, there are several derived stores (currentPage, logs, currentAccount, currentWallet, WalletsStore, NetworksStore, AccountStore, ContactsStore, SettingsStore) which are basically "views" into different parts of the AppStore. They return the respective part of the state when accessed.
