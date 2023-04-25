# 1. change defaultAdress:

1. path: src/api/subDomainRegistrar.js
2. this line: const defaultAddress = 'xxxxxx', replace xxxxxx to the contract address of ETHRegistrarController

# 2. change subgraph url

## 2.1

1. path: src/apollo/apolloClient.js
2. this line: '11155111': 'xxxxxx', replace xxxxxx to your subgraph url

## 2.2

1. path: .env
2. this line: REACT_APP_GRAPH_NODE_URI=xxxxxx, replace xxxxxx to your subgraph url

# 3. change ens contract address

1. path: src/apollo/mutations/ens.js
2. this line: ensAddress: 'xxxxxx', replace xxxxxx to the contract address of ENSRegistry

# 4. change web api url(Not Must)

1. path: src/rpcUrl.js
2. this line: export const rpcUrl = 'xxxxxx', replace xxxxxx to your web api url

# 5. build package

1. run command:

```sh
yarn
```

# 6. delete node_modules

# 7. add sepolia network ens address

## 7.1 root path

### 7.1.1 linux

root path: ls \$(yarn cache dir)/npm-@ethersproject-networks-5.6.2-2bacda62102c0b1fcee408315f2bed4f6fbdf336-integrity/node_modules/@ethersproject/networks/

### 7.1.2 windows

root path: dir "\$(yarn cache dir)/npm-@ethersproject-networks-5.6.2-2bacda62102c0b1fcee408315f2bed4f6fbdf336-integrity/node_modules/@ethersproject/networks/"

## 7.2

1. path: lib/index.js
2. this line: the before of

```js
kintsugi: { chainId: 1337702, name: "kintsugi" },
```

add the code :

```js
    sepolia: {
        chainId: 11155111,
        ensAddress: "xxxxxx",
        name: "sepolia",
        _defaultProvider: ethDefaultProvider("sepolia")
    },
```

and replace xxxxxx to the contract address of ENSRegistry, default ENSRegistry: 0x07EF7d99Da8ebc810F0A3713208F56550bCc7634

## 7.3

1. path: lib.esm/index.js
2. this line: the before of

```js
kintsugi: { chainId: 1337702, name: "kintsugi" },
```

add the code :

```js
    sepolia: {
        chainId: 11155111,
        ensAddress: "xxxxxx",
        name: "sepolia",
        _defaultProvider: ethDefaultProvider("sepolia")
    },
```

and replace xxxxxx to the contract address of ENSRegistry, default ENSRegistry: 0x07EF7d99Da8ebc810F0A3713208F56550bCc7634

## 7.4

1. path: src.ts/index.ts
2. this line: the before of

```js
kintsugi: { chainId: 1337702, name: "kintsugi" },
```

add the code :

```js
    sepolia: {
        chainId: 11155111,
        ensAddress: "xxxxxx",
        name: "sepolia",
        _defaultProvider: ethDefaultProvider("sepolia")
    },
```

and replace xxxxxx to the contract address of ENSRegistry, default ENSRegistry: 0x07EF7d99Da8ebc810F0A3713208F56550bCc7634

# 8 run build or start

1. run command:

```sh
yarn
```

2. run command:

```sh
yarn start
```
