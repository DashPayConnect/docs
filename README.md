# DashPay Connect JS Library


## Quick start

This guide will get you up and running quickly with our extension and JS library.

### Installation for user

Before you begin, make sure to install the DashPay Connect Extension from the Google Chrome Store.
(Note: The link is currently pending approval from Google Chrome Store Verification. Please check back soon for updates.)


### For developers

You have two options for using the DashPay Connect JS library: through Node.js or as a standalone CDN. Here's how you can set it up.

### NPM

In order to use this library in Node, you will need to add it to your project as a dependency.

Having [NodeJS](https://nodejs.org/) installed, just type in your terminal :

```sh
npm install @dashpayconnect/js-library
```

### CDN Standalone

For browser usage, you can also directly rely on unpkg

```
<script src="https://unpkg.com/@dashpayconnect/js-library"></script>
```


## Initialization

After you've installed the DashPay Connect library, you can initialize it like this:

#### NodeJS:

```js
const { Client } = require('@dashpayconnect/js-library');

const client = new Client();

(async ()=>{
await client.connect()
const account = client.getCurrentAccount();
})();
```

#### Browser:

```js
    const client = new DashPayConnect.Client();
    await client.connect()
    const {address, walletId, accountIndex, balance: accountBalance, walletType, accountPath} = client.getCurrentAccount();
    console.log(client.getCurrentAccount().accountIndex, accountIndex);
    console.log({address, walletId});
    await client.disconnect()
```

### Developing the Extension
For those interested in contributing to the DashPay Connect Extension, please also take a look at the boilerplate demo provided in the boilerplate folder.  
This is a simple index file that demonstrates how to use the DashPay Connect JS library to interact with the extension.  
Also the code that builds the extension itself is of interest.
