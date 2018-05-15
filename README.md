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
|FIXTURE_ACCOUNTS|Addresses of account for which fixtures were deployed|
|HEAD_BLOCK_NO|Block number at which deployment ends. It is useful for test setup. You should wait for this block before tests - your node is still deploying contracts|

Please read [platform-contracts README](https://github.com/Neufund/platform-contracts). for details
