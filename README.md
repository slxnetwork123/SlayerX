## SlayerX

Official Golang implementation of the SlayerX protocol.

Building `geth` requires both a Go (version 1.16 or later) and a C compiler. You can install
them using your favourite package manager. Once the dependencies are installed, run

```shell
make geth
```

or, to build the full suite of utilities:

```shell
make all
```


## To Run SlayerX

### Prerequisites
- System must have `go` installed 
- User must have metamask wallet address 
  - (Example: `0x285d0C039217572a24235D3Cb29a7c02a8F78354`)



- Download executable from the latest release
- After downloading unzip the `SlayerX`
- Find geth


### Run on Linux
- Initialize the DB
```javascript
./geth --datadir data init genesis.json
```

#### Method 1
- Start the geth using
```javascript
./geth --datadir data --mine --miner.threads=1 --miner.etherbase=0x285d0C039217572a24235D3Cb29a7c02a8F78354 --http.addr 127.0.0.1 --http.port 8546 --http.api "net,web3,eth,debug,txpool"
```


#### Method 1
> Step 1
- edit config.toml file & Change DataDir path

> Step 2
```javascript
./geth --config config.toml --miner.etherbase=0x285d0C039217572a24235D3Cb29a7c02a8F78354 --http --http.corsdomain=*
```

> Step 3
- attach to the running geth
```javascript
./geth attach data/geth.ipc
```

> Step 4
- Start stop mining
```javascript
admin.addPeer("enode://64e1050826d2ad7d1b2a11d3b21a8bebc9f7d98fe61c3565103d4fde324e58196494523e21f1feca8ac455d3dc4b0b176cd8b6e1fcb01b0b096323ef29f1f83b@134.122.48.108:30303")

miner.start(1) # to start mining
miner.stop() # to stop the mining
```

### Run on Windows
- Initialize the DB
```javascript
.\geth --datadir data init genesis.json
```

- Start the geth using
```javascript
.\geth --datadir data --miner.etherbase=0x285d0C039217572a24235D3Cb29a7c02a8F78354 --http.addr 127.0.0.1 --http.port 8546 --http.api "net,web3,eth,debug,txpool"
```

> Step 3
- attach to the running geth
```javascript
.\geth.exe attach ipc:\\.\pipe\geth.ipc

admin.addPeer("enode://64e1050826d2ad7d1b2a11d3b21a8bebc9f7d98fe61c3565103d4fde324e58196494523e21f1feca8ac455d3dc4b0b176cd8b6e1fcb01b0b096323ef29f1f83b@134.122.48.108:30303")

miner.start(1)
```


- Genesis file
```json
{
  "config": {
    "chainId": 9119,
    "homesteadBlock": 0,
    "eip150Block": 0,
    "eip155Block": 0,
    "eip158Block": 0,
    "byzantiumBlock": 0,
    "constantinopleBlock": 0,
    "petersburgBlock": 0,
    "istanbulBlock": 0,
    "berlinBlock": 0,
    "londonBlock": 0,
    "ethash": {}
  },
  "alloc": {
    "285d0C039217572a24235D3Cb29a7c02a8F78354": {
      "balance": "2000000000000000000000000"
    }
  },
  "coinbase": "0x0000000000000000000000000000000000000000",
  "difficulty": "0x200000",
  "extraData": "",
  "gasLimit": "0x1C9C380",
  "nonce": "0x0000000000000042",
  "mixhash": "0x0000000000000000000000000000000000000000000000000000000000000000",
  "parentHash": "0x0000000000000000000000000000000000000000000000000000000000000000",
  "timestamp": "0x6509BDE2"
}
```
