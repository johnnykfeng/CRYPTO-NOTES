	 ![[Investopedia_merkle_tree_figure.png]]

Merkle trees are a pattern of hashing the transactions (leaves) of a block e.g. Bitcoin's block has 10 minutes worth of transactions. Merkle trees serve as an efficient way to encode all the transactions of a block. Each transaction is first hashed once, then each pair of hashes from the transactions are hashed together, and so on for subsequent pairs of hashes (see figure), until one hash represents the whole block. That last hash is referred as the Merkle root. 

One advantage of Merkle trees is that you can verify a specific transaction without downloading the entire blockchain (562 GB as of April 2024). 
	For example, say that you wanted to verify that transaction TD is included in the block in the diagram above. If you have the root hash (HABCDEFGH), the process is like a game of sudoku: you query the network about HD, and it returns HC, HAB, and HEFGH. The Merkle tree allows you to verify that everything is accounted for with three hashes: given HAB, HC, HEFGH, and the root HABCDEFGH, HD (the only missing hash) has to be present in the data.

![[Merkle_tree_example.png]]