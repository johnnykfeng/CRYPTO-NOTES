SEC = Standards for Efficient Cryptography
DER = distinguished encoding rules

SEC and DER are two different standards for serializing a byte sequence. Both is used here.

The whole point of #Ch4 is to describe the methods for encoding the data such as Signatures, PrivateKeys and S256Points. There is a very elaborate way that bitcoin does it that is both memory efficient and secure. 

Recall that the S256Points in #Ch3, they can be converted to SEC format like this:

'04' + '(x-coordinate -32 bytes)' + '(y-coordinate -32 bytes)'
