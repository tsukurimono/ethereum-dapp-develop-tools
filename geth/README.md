# Private network

## Setup
```
$ sudo docker-compose up -d
$ sudo docker exec -it miner sh
# mkdir data
# geth account new --datadir ./data
```

## Sample Account
```
Password: password
Public address of the key:   0x396AdC08A8872D2D39e2F9b0E6643225017C3c96
Path of the secret key file: data/keystore/UTC--2022-01-29T11-43-31.515464655Z--396adc08a8872d2d39e2f9b0e6643225017c3c96
``` 
Note: This is a sample account to explain each command below.

## Init

### Miner
```
$ sudo docker exec -it miner sh
# geth --datadir ./data init genesis.json
# geth --datadir ./data --networkid 3792 --port 30303 --http --http.api "eth,web3,personal,net,miner,admin,debug" --http.port 8507 --http.addr "0.0.0.0" --allow-insecure-unlock --nodiscover --http.corsdomain "*" --mine --miner.threads 1 --miner.etherbase 0x396AdC08A8872D2D39e2F9b0E6643225017C3c96 console
```
### Client
```
$ sudo docker exec -it client sh
# geth --datadir ./data init genesis.json
# geth --datadir ./data --networkid 3792 --port 30303 --http --http.api "eth,web3,personal,net,miner,admin,debug" --http.port 8507 --http.addr "0.0.0.0" --allow-insecure-unlock --nodiscover --http.corsdomain "*" console
```

```
> admin.addPeer("enode://5a256813b2188c4cb26a8ab1cd3e9199bad32885f9a066c06cd5c4318ed184c288eb76d77105b3ffc0443f0375f676bf46989db7648ada3fde0ef86b7a15fc84@miner:30303")
> admin.peers
```

# Goerli network

## goerli node
```
$ sudo docker-compose -f docker-compose-goerlinode.yml up -d
```

### Command
__attach console__
```
$ sudo docker exec -it goerli sh
# geth attach data/geth.ipc
```
