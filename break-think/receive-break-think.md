# Receive Flow Break Think
Here is most important functions.
## _lzReceive(...)

```text
INVARIANT

1. Only authentic LZ message from the trusted contract can trigger _lzReceive().

2. The decoded recipient must match the recipient that was encoded on source chain.

3. The decoded amount must match the recipient that was encoded on source chain.


```
