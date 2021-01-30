# Diploma Generation and Verification Using Blockchain

## Introduction
###### Academic certificates are highly esteemed as they serve as an indicator of the human capital of their bearers. Human capital refers to the skills, competencies, knowledge and aptitudes achieved through education. Academic qualifications are particularly important in employment situations as they serve as a guarantee of not just the knowledge, expertise and skills of the holders but also of their abilities, reliability and dedication . Academic qualifications are deemed to be genuine when they are conferred by a university that is legally authorized to award such certificates.  
  
##
  

###### Because they are so valuable, people often lie about their academic qualifications by producing fake certificates. In the United States there are currently 2 million fake degree certificates in circulation and 300 unauthorized universities operating. The United Sates has the highest number of fake institutions in the world followed by the United Kingdom which has about 270 fake institutes. A study found that up to 35% of candidates in Australia falsified their academic credentials for the sake of employment. observed that most candidates lie at least about some part of their educational credentials and experience. mentioned that academic certification.

##

##### In this Project we are going to propose a solution to this problem based on blockchain.

##

## Blockchain
###### Blockchain technology is not only a single technique, it is a combination of many techniques such as cryptography, mathematics, algorithms and distributed consensus algorithms. A blockchain is composed of six key elements as follows:
- **Decentralized**: Blockchain doesn’t have to rely on a single centralized node any more like a master node, each node can record, store and update the ledger, and together they form the blockchain.
- **Transparent**: The block’s data recorded by each node and distributed among other connected nodes is visible to each node which creates transparency among connected nodes.
- **Anonymous**: In order to make the transactions anonymous, data is hashed before sharing by using a secure algorithm.
- **Consensus Base**: Since node are publicly connected on blockchain and changes can only happen when majority of nodes accept the change, all nodes are eligible to transfer and update data safely providing a consensus base to the system.
- **Immutable**: All records are permanently kept which cannot be altered unless someone can take control of more than 51% nodes simultaneously.
- **Open Source**: Most Blockchain systems are open to everyone, allowing participants to modify the code and technology in ways that best suits their needs. However this does not mean that anyone can modify a running blockchain solution. Making any modification to a running solution means all connected nodes are publicly accepting the change.

### Blockchain Structure

###### Each block in the blockchain contains five elements which are:
- **The main data**: The data depends on the type of transaction; it is generally a transfer between nodes A and B however it can be of any type like money transfer or record transfer.
- **The hash of the pervious block**: When a transaction is executed, its hash is generated and broadcasted to the network. There are several hashing algorithms in use but the most dominant is the Merkle Tree. This algorithm allows easy hash and easy de-hash options which is why Merkle Trees is a common choice.
- **The hash of the current block**: The final hash value is recorded in block header (hash of current block), while the content itself is stored in the body of the block. Blocks are generally bound to a size hence allowing a limited number of transactions per block.
- **The timestamp**: The time the block was generated.
- **Other information**: Like signature of the block, Nonce value, or other data that the user defines. The data structure of a typical blockchain application is indicated in the Figure below

![Blockchain Structure](https://miro.medium.com/max/2426/0*mKiuqGLo9nsfDHLo.png)

##
##
##
##
##
##

![Diploma Generation Flowchart](https://i.ibb.co/x8bLffV/Flowchart.png)

##
##
##
##
##

![Diploma Verification Flowchart](https://i.ibb.co/sV6SCKd/Flowchart-1.png)

##
##
##
##
##

## Tools

### Ganache

###### Ganache provides us our personal local blockchain network which we can use to develop our blockchain application. It also gives temporary test accounts with fake ethereum which we can use to run our apps.

##
##
##
![Ganache Dashboard](https://www.trufflesuite.com/img/ganache-window.png)

##
##
##
##
##
##

## RPC Server
###### RPC, or Remote Procedure Call, allows client and server app to communication on a network. The RPC server "allows remote clients to connect, pass commands, and transfer data using the RPC protocol."

##
##
##
##
##
##

## Rinkeby

###### Rinkeby is an Ethereum testnet (or test network). Testnets are typically used by developers to run "tests" for their application or software. Currency on testnet are valueless.
##### Our project is using Ethereum on local blockchain setup and deployed on Rinkeby test network.

##
##
##
##


![Rinkeby Dashboard](https://habrastorage.org/webt/b7/cx/f9/b7cxf9o6oxtiaciuvg4cafsztnk.jpeg)

##
##
##
##

## MongoDB
MongoDB is a source-available cross-platform document-oriented database program. Classified as a NoSQL database program, MongoDB uses JSON-like documents with optional schemas.


## Steps to set up local development environment

### Setting local blockchain

1. We need to install CLI version of Ganache.

   ```bash
   npm install -g ganache-cli
   ```

   > We need to start the RPC server before running our application.

1. To start the RPC server run the command

   ```bash
   npm run ganache
   ```

   > Windows user will need to run this command in separate command prompt or terminal.

1. Deploy the smart contract to the local blockchain.

   ```bash
   npm run contract-deploy
   ```

> The above 2 steps need to be run everytime we are running the project.

### Setting local database

> MongoDB server should be running as a background Process

1. Open mongo in terminal using command `mongo`

1. Then change the db using command

   ```bash
   use diploma
   ```

1. Then set DB user and password with the following command

   ```javascript
   db.createUser({
     user: "<YOUR USER NAME>",
     pwd: "<YOUR USER PASSWORD>",
     roles: [{ role: "dbOwner", db: "diploma" }]
   });
   ```

1. Include these username and password in the `.env` file.

### Now we can start the server

```bash
npm start
```

## Deploying Smart Contract

The contract can be deployed in any test networks. We are using Rinkeby test network with help of truffle.

1. First of all we need to have a metamask account. When we create an account in metamask a _mnemonic_ is given to us.

2. After that create a project in [Infura](https://infura.io). This will help us to use rinkeby network through infura.

3. You will get an endpoint like this `https://rinkeby.infura.io/yourapikey`.

4. Create a `.env` file in root directory and paste the previously genrated mnemonic and the endpoint URL in that. 

 

5. Now we can deploy the smart contract using a single command:

   ```BASH
   npm run deploy
   ```

6. We will get a contract address of newly generated contract. Save this for further uses.

## Testing app

To test the app run the command `truffle test`.

![Diploma](https://i.ibb.co/XkJVbxm/Untitled.png)
---
