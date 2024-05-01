Blockchain with Python and React

Blockchain Implementation
Block Class (block.py)
The Block class represents a unit of storage in a blockchain, storing transactions that support a cryptocurrency.

Attributes:
timestamp: Represents the time when the block was created.
last_hash: Represents the hash of the previous block in the blockchain.
hash: Represents the hash of the current block.
data: Stores the data associated with the block.
Methods:
__init__(self, timestamp, last_hash, hash, data): Initializes a new block with the provided timestamp, last hash, hash, and data.
__repr__(self): Returns a string representation of the block including its timestamp, last hash, hash, and data.
mine_block(last_block, data): Static method to mine a new block based on the given last block and data.
genesis(): Static method to generate the genesis block, which is the initial block in the blockchain.
Blockchain Class (blockchain.py)
The Blockchain class represents a public ledger of transactions, implemented as a list of blocks - data sets of transactions.

Attributes:
chain: Represents the list of blocks in the blockchain. It is initialized with the genesis block.
Methods:
__init__(self): Initializes a new blockchain with the genesis block as the first block in the chain.
add_block(self, data): Adds a new block to the blockchain with the provided data.
__repr__(self): Returns a string representation of the blockchain, showing all blocks in the chain.
Crypto Hash Module (crypto_hash.py)
The crypto_hash module provides a function for generating SHA-256 hashes of data.

Functions:
crypto_hash(data): Generates the SHA-256 hash of the provided data. The data is first converted to a JSON string using json.dumps(). Returns the hexadecimal representation of the hash.

Block Hash
A block hash is generated using the SHA-256 algorithm. SHA-256 produces a fixed-size hash of 256 bits, ensuring security and integrity of data. Even a slight change in the input data results in a completely different hash. This property makes SHA-256 a one-way function, meaning it cannot be reversed to obtain the original data. It's designed in such a way that guessing and checking to reverse the hash is practically infeasible.

Blockchain utilizes SHA-256 to validate blocks. By regenerating the hash and comparing it to the original hash provided, we can detect if the data within a block has been tampered with.

Encoding and Decoding
Encoding involves converting data into an alternative representation. For example, UTF-8 encoding represents characters using 8-bit units. Decoding, on the other hand, reverses the process, converting encoded data back into its original format.