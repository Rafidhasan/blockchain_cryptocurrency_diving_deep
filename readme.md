## Commands
1. npm init - initializing package.json in the project.
2. npm i jest - jest for testing the function.
3. npm run test - starting test with npm.

## Files
1. config.js - has the genesis block
2. block.js - {
    connects the genesis blocks,
    construct one block,
    mines block
}
3. blockchain.js - {
    adds block,
    replaces block,
    check chain validation
}
4. crypto-hash.js - {
    update hash variable with SHA-256
}

## Test Files and Rules
1. block.test.js - {
    Gives static variables to block 
    ### Rules 
    1. Describing main block class {
        1. Has timestamp, lastHash, hash and data property
    }

    2. Describing Genesis block {
        1. Genesis block returns a block instance
        2. Genesis block returns GENESIS_DATA
    }

    3. Describing mine block {
        1. Returns block instance,
        2. It sets the last hash value to be hash value of last block
        3. It has the actual data
        4. It creates SHA-256 hash based on proper inputs
    }
}

2. blockchain.test.js - {
    ### Rules
    1. Describing core blockchain {
        1. It contains a chain array instance
        2. It starts with genesis block
        3. Adds a new block to the chain
    }

    2. Chain Validation {
        1. When the chain does not start with the genesis block , it returs false.
        2. When the chain starts with genesis block and has multiple blocks - {
            If lastHash reference has changed, it returns false.
            If he chain contains a block with an invalid field, it returns false.
            If the chain does not contain any invalid blocks, it returns true.
        }
        3. 
    }
}
