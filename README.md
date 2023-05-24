# Solidity dApps with React and Truffle Box
Chapter 3: Step-by-step building web3 smart contract with react truffle box, solidity, and ABI (Application Binary Interface)

Decentralized applications (dApps) have become increasingly popular in recent years due to the transparency, security, and immutability provided by blockchain technology. Developing dApps requires knowledge of blockchain programming languages such as Solidity, as well as web development technologies such as React. 

Truffle Box is a popular tool that provides developers with pre-built project templates for building dApps. By combining Solidity, React, and Truffle Box, developers can create powerful and secure dApps that leverage the benefits of blockchain technology. 

In this chapter, we will explore the process of building dApps using Solidity, React, and Truffle Box. We will cover the essential concepts and tools needed to build decentralized applications, including the basics of Solidity, the React framework, and Truffle Box project templates. We will also demonstrate how to integrate these technologies to create a full-stack dApp, highlighting best practices and common pitfalls along the way.

## The Chapters
- Chapter 1: [Solidity Remix Basic Syntax](https://github.com/kecci/solidity-remix-basic)
- Chapter 2: [Simulation VM with Ganache and MetaMask for Solidity Smart Contract](https://github.com/kecci/solidity-truffle-ganache-remix)
- Chapter 3: [Building Simple Decentralized Application with React and Truffle Box](https://github.com/kecci/solidity-react-truffle-box) (you in here)

## Table of Contents
- [Solidity dApps with React and Truffle Box](#solidity-dapps-with-react-and-truffle-box)
  - [The Chapters](#the-chapters)
  - [Table of Contents](#table-of-contents)
  - [ABI (Application Binary Interface)](#abi-application-binary-interface)
    - [Connecting Smart Contract to Website](#connecting-smart-contract-to-website)
    - [How ABI works ?](#how-abi-works-)
    - [ABI vs API](#abi-vs-api)
  - [React Truffle Box](#react-truffle-box)
    - [Install npm \& npx with nvm (version manager)](#install-npm--npx-with-nvm-version-manager)
    - [React-Truffle Installation](#react-truffle-installation)
    - [FAQ](#faq)
  - [Setup Ganache with Truffle Box](#setup-ganache-with-truffle-box)
    - [I. Ganache workspace](#i-ganache-workspace)
    - [II. Truffle Compile](#ii-truffle-compile)
    - [III. Truffle Test](#iii-truffle-test)
    - [IV. Ganache Contract](#iv-ganache-contract)
    - [V. Truffle Migrate](#v-truffle-migrate)
  - [Run Client (React Truffle Box)](#run-client-react-truffle-box)
    - [Run web application](#run-web-application)
    - [Open web application](#open-web-application)
  - [Source](#source)
  - [Conclusion](#conclusion)

## ABI (Application Binary Interface)
![ABI](/assets/ABI-Diagram.png)

Application Binary Interface (ABI) is a standardized interface for communication between different software modules, often between a high-level language and a low-level language or hardware. In the context of blockchain technology, an ABI specifies the rules for encoding and decoding messages that are sent between smart contracts on the blockchain network.

An ABI is critical for enabling communication between smart contracts written in different programming languages, allowing them to interact with each other seamlessly. ABI defines the structure of the data that is passed between the contracts and the types of functions that can be called. It provides a clear and well-defined interface that ensures that the contracts interact with each other in a standardized and secure manner.

ABI plays an essential role in the development of decentralized applications (dApps) that run on blockchain networks. It provides developers with a standardized way of communicating with smart contracts, making it easier to create complex applications that interact with multiple smart contracts. Moreover, ABI enables the creation of libraries and modules that can be reused across different smart contracts, reducing development time and costs.

[Application Binary Interface](https://www.youtube.com/watch?v=fP5lu_E7AY0&list=PLH1gH0TmFBBhvZi4kEqU6kCjyv_y8qBae&index=35)

### Connecting Smart Contract to Website
1. Install Web3Js
2. **ABI & Bytecode**
3. Address Smart Contract

### How ABI works ?
- Smart contract needs to compile in bytecode at EVM (Ethereum Virtual Machine)
- Smart contract deployed will generate bytecode are saved in blockchain in an address.
- In EVM and Ethereum, Smart contract only bytecode orders
- All functions that defined in smart contract, user need to translate names and arguments in bytecode representation.
- To be interpreted, byte that sent by user need to re-convert in tuple (dictionary).
- All format above are ABI.


### ABI vs API
- ABI looks like API
- ABI defines method and structure that used to interact with binary contract.
- ABI handled by compiler, like a Remix.
- ABI are in the form of a JSON.

ABI Example (json format)
![img](assets/ABI-Format-json.png)

or you can see on the `/client/src/contracts/SimpleStorage.json` after you do truffle compile. Please read [II. Truffle Compile](#ii-truffle-compile)

## React Truffle Box
This box comes with everything you need to start using Truffle to write, compile, test, and deploy smart contracts, and interact with them from a React app.

### Install npm & npx with nvm (version manager)
This is not mandatory, but I do love version manager so you can use nvm for installing npm and npx (if you don't have npm before).
- https://github.com/nvm-sh/nvm

Download & Install:
```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash
```

Intallation Command, you can choose between:
```
# Install the latest available version
nvm install node

# Install the latest LTS version
nvm install --lts

# Install a specific version number
nvm install 8.0.0
```

### React-Truffle Installation

First ensure you are in an empty directory.

Run the `unbox` command using 1 of 2 ways.

```sh
# Install Truffle globally and run `truffle unbox`
$ npm install -g truffle
$ truffle unbox react
```

```sh
# Alternatively, run `truffle unbox` via npx
$ npx truffle unbox react
```

Start the react dev server.

```sh
$ cd client
$ npm start
```

From there, follow the instructions on the hosted React app. It will walk you through using Truffle and Ganache to deploy the `SimpleStorage` contract, making calls to it, and sending transactions to change the contract's state.

### FAQ

- __How do I use this with Ganache (or any other network)?__

  The Truffle project is set to deploy to Ganache by default. If you'd like to change this, it's as easy as modifying the Truffle config file! Check out [our documentation on adding network configurations](https://trufflesuite.com/docs/truffle/reference/configuration/#networks). From there, you can run `truffle migrate` pointed to another network, restart the React dev server, and see the change take place.

- __Where can I find more resources?__

  This Box is a sweet combo of [Truffle](https://trufflesuite.com) and [Webpack](https://webpack.js.org). Either one would be a great place to start!

## Setup Ganache with Truffle Box

Source: https://www.youtube.com/watch?v=Qy_95FYLM_k&list=PLH1gH0TmFBBhvZi4kEqU6kCjyv_y8qBae&index=36

### I. Ganache workspace
Setting Truffle Projects to your `truffle-config.js`
![ganache](assets/Ganache%20-%20Setting%20Truffle%20Projects.png)

Setting your `truffle-config.js` to like this.
![truffle](assets/Truffle%20-%20Setting%20truffle%20json%20for%20development.png)

### II. Truffle Compile
command
```
cd truffle
npx truffle compile
```

### III. Truffle Test
command
```
cd truffle
npx truffle test
```

example output
```
Using network 'test'.


Compiling your contracts...
===========================
> Compiling ./test/SimpleStorageTest.sol
> Artifacts written to /var/folders/p1/3r66895x1296c01c8p3t1sfr0000gn/T/test--82799-x8m2Gga0B2JI
> Compiled successfully using:
   - solc: 0.8.18+commit.87f61d96.Emscripten.clang


  SimpleStorageTest
    ✔ testWriteValue (57ms)

  Contract: SimpleStorage
    ✔ should read newly written values (53ms)


  2 passing (3s)
```

### IV. Ganache Contract
TBD

### V. Truffle Migrate
command
```
cd truffle
npx truffle migrate
```

output sample
```
Compiling your contracts...
===========================
> Everything is up to date, there is nothing to compile.


Starting migrations...
======================
> Network name:    'development'
> Network id:      5777
> Block gas limit: 6721975 (0x6691b7)


1_deploy_simple_storage.js
==========================

   Replacing 'SimpleStorage'
   -------------------------
   > transaction hash:    0x8659dd54c24628b094de5f9d3ee3f6a8b2b400176b886006b3a64381b56151f3
   > Blocks: 0            Seconds: 0
   > contract address:    0x6E1d0Fc9598119187094e8990736fD7638384593
   > block number:        1
   > block timestamp:     1684918908
   > account:             0x1daD53748b5130C8EBf96Fc858386c61Af24F9b9
   > balance:             99.999575921125
   > gas used:            125653 (0x1ead5)
   > gas price:           3.375 gwei
   > value sent:          0 ETH
   > total cost:          0.000424078875 ETH

   > Saving artifacts
   -------------------------------------
   > Total cost:      0.000424078875 ETH

Summary
=======
> Total deployments:   1
> Final cost:          0.000424078875 ETH
```

Ganache contracts result
![migrate](assets/Ganache%20-%20migrate%20contract%20results.png)

## Run Client (React Truffle Box)

### Run web application
command
```
cd client
npm start
```

output
```
> truffle-client@0.1.0 start
> webpack serve

<i> [webpack-dev-server] Project is running at:
<i> [webpack-dev-server] Loopback: http://localhost:8081/
<i> [webpack-dev-server] On Your Network (IPv4): http://192.168.151.210:8081/
<i> [webpack-dev-server] On Your Network (IPv6): http://[fe80::1]:8081/
<i> [webpack-dev-server] Content not from webpack is served from '/Users/abyankecci/go/src/github.com/kecci/solidity-react-truffle-box/client/public' directory
3 assets
78 modules
webpack 5.75.0 compiled successfully in 1987 ms
```

### Open web application

Open: http://localhost:8081/

Transaction Simulation
![trx](assets/React%20-%20Sample%20transaction.gif)

Ganache Result after transaction
![trx](assets/Ganache%20-%20after%20trx%20transactions.png)
![contracts](assets/Ganache%20-%20after%20trx%20contracts.png)


## Source
- Ipung Dev:
  - ABI: https://www.youtube.com/watch?v=fP5lu_E7AY0&list=PLH1gH0TmFBBhvZi4kEqU6kCjyv_y8qBae&index=35
  - React Truffle Box Installation: https://www.youtube.com/watch?v=Qy_95FYLM_k&list=PLH1gH0TmFBBhvZi4kEqU6kCjyv_y8qBae&index=36
- Facundo Carballo
  - ToDo Task: https://www.youtube.com/watch?v=cyKvTo89HRY
- Budi Winarno
  - Simple Dapp: https://www.youtube.com/watch?v=yHdoHqqo3JA
- Code Coliseum
  - Basic App: https://www.youtube.com/watch?v=AKXFziwYUWE
- Web Dev Cody
  - Buy Ticket Simulation: https://www.youtube.com/watch?v=JXa_Y-17Oj4
- One More Journey
  - Pete's Pet Shop: https://www.youtube.com/watch?v=kkiaBPcnc6U&list=PLde8eDss7CuQLM46HkFKnTyTNoKccQanI

## Conclusion
Congratulations! you already finished following the chapters of building Decentralized Applications. After this you can start: 
1. Modify your `.sol` contracts on `/truffle` folder as you needed for your application. (You can following the chapter 1 and 2 for the contracts example)
2. Modify your `EthProvider.jsx` and others on `/client/src` folder as you needed for your application. (You can following other tutorial for build react js apps)
3. Done, you have your DApp ready to deploy !

Maybe for deploy section would be in another chapter.