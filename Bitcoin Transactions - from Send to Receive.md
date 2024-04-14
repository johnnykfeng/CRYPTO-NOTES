
https://www.youtube.com/watch?v=ZPFL6R-voW0

## 3 parts to Send to Receive:
1. **Signing**
2. **Broadcasting** 
3. **Confirming**

### Signing
Alice wants to send Bob some bitcoins. Bob sends a public address Alice and she hits the send button for 1 btc. After that, a TX (transaction) message is created with info such as Sender, Recipient, Amount being sent. 

A unique digital signature is produced cryptographically from the private key of Alice. This signature is different for every transaction.

The signature and TX message is grouped into a small transaction file (TX file). 

### Broadcasting
The TX file is broadcasts to all the btc nodes in the network. Each node checks the TX file and signature to verify it - like a bank that verifies your account balance before clearing your cheque. 

When a node receives a TX file, it keeps it in a holding area called Mempool (short for "memory pool"). This concludes the broadcasting step.

### Confirming
Miners group the TX files together from the Mempool and create a "block". There is a limit to the number of TX files put in a block, so the TX that pays the highest mining fees are prioritized. Miners compete with each other to get their block into the blockchain, based on solving a mathematical computation. The miner with the most computational power has the best chance of winning. Once the winner is chosen, and the block is appended to the blockchain, all the TXs in the block are considered "confirmed".

Metaphor
The miners are writing the history book of btc transactions, the winner of each mining block gets the write the next page.