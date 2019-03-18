# demo-blockchain

A basic implementation of blockchain in Python as described in post ["Learn Blockchain by Building One"](https://hackernoon.com/learn-blockchains-by-building-one-117428612f46).

# Usage

## Starting a node

You can start as many nodes as you want with the following command:

`python blockchain.py -p <port-number>`

## Endpoints

### Mine new block

* `GET http://localhost:5000/mine`

### Create a new transaction to a block

* `POST http://localhost:5000/transactions/new`

* __Body__: A transaction to be added

  ```json
  {
	"sender": "f66db21a57ff480f92572a135fe36290",
	"recipient": "someone-other-address",
	"amount": 5
  }
  ```

### Request the full Blockchain

* `GET http://localhost:5000/chain`

### Register new nodes in the network
Currently you can add a maximum of 10 nodes.

* `POST http://localhost:5000/nodes/register`

* __Body__: A list of nodes to add

  ```json
  {
     "nodes": ["http://127.0.0.1:5001", <more-nodes>]
  }
  ```

### Resolve any conflicts to ensure a node has the correct chain.

* `GET http://localhost:5000/nodes/resolve`

### Request the block hash.

* `GET http://localhost:5000/chain/block/<block-number>`