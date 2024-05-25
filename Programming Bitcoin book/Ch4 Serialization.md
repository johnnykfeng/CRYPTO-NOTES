SEC = Standards for Efficient Cryptography
DER = distinguished encoding rules

SEC and DER are two different standards for serializing a byte sequence. Both is used here.

The whole point of #Ch4 is to describe the methods for encoding the data such as Signatures, PrivateKeys and S256Points. There is a very elaborate way that bitcoin does it that is both memory efficient and secure. 

## SEC S256Points
Recall that the S256Points in #Ch3, they can be converted to SEC format like this:

$'04' + '(x-coordinate -32 bytes)' + '(y-coordinate -32 bytes)'$
Or in python code
```python
class S256Point(Point):
...
	def sec(self):
		return b'\x04' + self.x.num.to_bytes(32, 'big') + \
		self.y.num.to_bytes(32, 'big')
```

The compressed SEC format is also quite simple. We just use the prefix marker '02' if y is even or '03' if y is odd, and then append the x-coordinate. 

To parse the SEC formatted binary back into S256Point, the steps are as follows:
1. Determine if SEC format is uncompressed or compressed based on the first binary byte
	* If uncompressed, just read out the first and second halfs of the remaining string
2. If compressed, determine the evenness of the y-coordinate
3. Take the square root of the right side of the elliptic curve equation to get $y$
4. Return the correct point based on evenness determined in step 2

## DER signatures
DER format is a bit more complicated. The signature is both the $r$ and $s$ value, and they cannot be derived from each other like $x$ and $y$ coordinates in S256 points. 

Here's a screenshot of figure 4-4 in the book

![[DER format. Figure 4-4.png]]


## Base58 encoding for sharing public keys


## WIF formats for passing private (secret) keys

