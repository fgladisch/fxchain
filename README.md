# anychain

Put a blockchain in your life!

## Quick Start

```ts
import { Block, Blockchain } from "@anychain/core";

interface User {
	id: number;
	firstName: string;
	lastName: string;
}

const blockchain: Blockchain<User> = new Blockchain<User>();

blockchain.add({
	id: 42,
	firstName: "Elon",
	lastName: "Musk"
});
```

## API

### #toJSON()

The method `blockchain.toJSON()` will output the following JSON for the example above:

```json
[
	{
		"index": 0,
		"predecessor": null,
		"data": "GENESIS",
		"time": 1522053753184,
		"hash": "42eb51b086fadc504ca3f494e6332788a008c8aff7b7369d22268540e55f1854"
	},
	{
		"index": 1,
		"predecessor": "42eb51b086fadc504ca3f494e6332788a008c8aff7b7369d22268540e55f1854",
		"data": {
			"id": 42,
			"firstName": "Elon",
			"lastName": "Musk"
		},
		"time": 1522053753184,
		"hash": "45c102b6b73fcab0f1396079c94a863640d0927205b3f0803702f047155412f8"
	}
]
```

### #getChain()

Returns the full chain as array.

### #getGenesisBlock()

Returns the first block in the chain (genesis).

### #getLatestBlock()

Returns the latest block in the chain.