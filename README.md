# Platform Smart Contracts Build Artifacts
Truffle build artifacts are stored in folders with the name of network that was deployed. Each folder contains `meta.json` with deployment parameters and `contracts` with a copy of Truffle `build` folder.
* ABIs may be obtained from `<network>/contacts/*.json` contract artifact.
* `Universe` address and other useful info exists in `meta.json`.

|Element|Description|
|-------|-----------|
|CONFIG|Copy of the deployment configuration which contains, among others, parameters passed to constructors etc.|
|DEPLOYER|Ethereum account that deployed contracts|
|UNIVERSE_ADDRESS|Address of the `Universe` contracts, from which all other addresses should be obtained (root of trust)|
|ROLES|Roles known to platform|
|ROLE_ADDRESSES|Role assignment at deployment|
|KNOWN_INTERFACES|Interfaces to services that were configured in `Universe`. Useful to obtain all relevant contract addresses|
|INTERFACE_ARTIFACTS|Names of contracts and thus Truffle artifacts that implement known interfaces, may be useful for automatic wrapper generation|
|NETWORK|Definition of Truffle network used to deploy. In most cases the host and port will not be public addresses so components connecting to Ethereum network should not use them|
|HEAD_BLOCK_NO|Block number at which deployment ends. It is useful for test setup. You should wait for this block before tests - your node is still deploying contracts|
|INITIAL_BLOCK_NO|Block number at which deployment starts. This is not block of first transaction though - just very close to it but earlier (fix deployment if you need better ;>)

Please read [platform-contracts README](https://github.com/Neufund/platform-contracts). for details

## Fixture description file
For dev deployment (`localhost`) a file describing fixture accounts is provided in `fixtures.json`. It contains various balances, states and flags coming from platform contracts. Example
```
"0x429123b08df32b0006fd1f3b0ef893a8993802f3": {
    "ethBalance": "999953070883955000000000",
    "neuBalance": "57611850597957803587524",
    "euroBalance": "0",
    "ethTokenBalance": "0",
    "icbmEuroBalance": "0",
    "icbmEthTokenBalance": "0",
    "euroLockBalance": [
      "0",
      "0",
      "0"
    ],
    "etherLockBalance": [
      "0",
      "0",
      "0"
    ],
    "icbmEuroLockBalance": [
      "0",
      "0",
      "0"
    ],
    "icbmEtherLockBalance": [
      "61128979800000000000",
      "57611850597957803587524",
      "1577029736"
    ],
    "identityClaims": "0x0000000000000000000000000000000000000000000000000000000000000000",
    "name": "ICBM_ETH_NOT_MIGRATED_NO_KYC"
  }
```