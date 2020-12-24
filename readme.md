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
            1. If lastHash reference has changed, it returns false.
            2. If he chain contains a block with an invalid field, it returns false.
            3. If the chain does not contain any invalid blocks, it returns true.
        }
    }

    3. Replace chain rules {
        1. When the new chain is not longer {
            1. It does not replace the chain
            2. It logs an error
        }

        2. When the new chain is longer {
            1. If the chain is invalid {
                1. It does not replace the chain
                2. It logs an error
            }
        }

        3. When the chain is valid {
            1. It does replace the chain
            2. It logs
        }
    }
}

3. crypto-hash.test.js - {
    ## Rules
    1. It generates a SHA-256 hashed output
    2. It produeces the same hash with the same input arguments in any order
}
