# Core-Geth DAppNode package for BSC

[![DAppNodeStore Available](https://img.shields.io/badge/DAppNodeStore-Available-brightgreen.svg)](http://my.dappnode/#/installer/binance-smart-chain.dnp.dappnode.eth)

[![Core-Geth github](https://img.shields.io/badge/Core--Geth-Github-blue.svg)](https://github.com/etclabscore/core-geth)

You can use this package without installing it in your DAppNode following these instructions:

## Prerequisites

- git

   Install [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) commandline tool.

- docker

   Install [docker](https://docs.docker.com/engine/installation). The community edition (docker-ce) will work. In Linux make sure you grant permissions to the current user to use docker by adding current user to docker group, `sudo usermod -aG docker $USER`. Once you update the users group, exit from the current terminal and open a new one to make effect.

- docker-compose

   Install [docker-compose](https://docs.docker.com/compose/install)
   
**Note**: Make sure you can run `git`, `docker ps`, `docker-compose` without any issue and without sudo command.

## Buidling

`docker-compose build`

## Running

### Start

`docker-compose up -d`

### View logs

`docker-compose logs -f`

### Stop

`docker-compose down`

## Extra options

You can edit the `docker-compose.yml` and add extra options, such as:
```
 - EXTRA_OPTS=--ws.api eth,net,ssh,miner,web3,personal,admin,txpool
```

## Connect using web3js
HTTP (uses port 8545):
   If the package is running and you're connected to your dappnode you can use:
   ```
   var Web3 = require('web3');
   var web3 = new Web3('http://binance-smart-chain.dappnode:8545')
   web3.eth.getBlockNumber().then(console.log)
   ```
   In case you are running it locally:
   ```
   var Web3 = require('web3');
   var web3 = new Web3('http://127.0.0.1:8545')
   web3.eth.getBlockNumber().then(console.log)
   ```
   
WEBSOCKETS (uses port 8546):
   If the package is running and you're connected to your dappnode you can use:
   ```
   var Web3 = require('web3');
   var web3 = new Web3('ws://binance-smart-chain.dappnode:8546')
   web3.eth.getBlockNumber().then(console.log)
   ```
   In case you are running it locally:
   ```
   var Web3 = require('web3');
   var web3 = new Web3('ws://127.0.0.1:8546')
   web3.eth.getBlockNumber().then(console.log)
   ```

## License

This project is licensed under the GNU General Public License v3.0 - see the [LICENSE](LICENSE) file for details
