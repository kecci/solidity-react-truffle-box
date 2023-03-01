# solidity-react-truffle-box
Chapter 3: Step-by-step building web3 smart contract with react truffle box, solidity, and ABI (Application Binary Interface)

## The Chapters
- Chapter 1: https://github.com/kecci/solidity-remix-basic
- Chapter 2: https://github.com/kecci/solidity-truffle-ganache-remix
- Chapter 3: https://github.com/kecci/solidity-react-truffle-box (you in here)

## Table of Contents
- [solidity-react-truffle-box](#solidity-react-truffle-box)
  - [Step Parts](#step-parts)
  - [Table of Contents](#table-of-contents)
  - [ABI (Application Binary Interface)](#abi-application-binary-interface)
  - [React Truffle Box](#react-truffle-box)
    - [Installation](#installation)
    - [FAQ](#faq)
  - [Setup Ganache with Truffle Box](#setup-ganache-with-truffle-box)
    - [I. Ganache workspace](#i-ganache-workspace)
    - [II. Truffle Compile](#ii-truffle-compile)
    - [III. Truffle Test](#iii-truffle-test)
    - [IV. Ganache Contract](#iv-ganache-contract)
    - [V. Truffle Migrate](#v-truffle-migrate)
  - [Run Client (React Truffle Box)](#run-client-react-truffle-box)
    - [Run NPX](#run-npx)
    - [Connect to Metamask](#connect-to-metamask)
  - [Source](#source)

## ABI (Application Binary Interface)
[Application Binary Interface](https://www.youtube.com/watch?v=fP5lu_E7AY0&list=PLH1gH0TmFBBhvZi4kEqU6kCjyv_y8qBae&index=35)

## React Truffle Box
This box comes with everything you need to start using Truffle to write, compile, test, and deploy smart contracts, and interact with them from a React app.

### Installation

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

### I. Ganache workspace
[TBD](https://www.youtube.com/watch?v=Qy_95FYLM_k&list=PLH1gH0TmFBBhvZi4kEqU6kCjyv_y8qBae&index=36)

### II. Truffle Compile
TBD

### III. Truffle Test
TBD

### IV. Ganache Contract
TBD

### V. Truffle Migrate
TBD

## Run Client (React Truffle Box)

### Run NPX
TBD

### Connect to Metamask
TBD

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
