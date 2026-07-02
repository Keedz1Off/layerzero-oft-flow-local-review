# 12 - endpoint.send(...)

## Function Code

```solidity
return
    endpoint.send{ value: messageValue }(
        MessagingParams(
            _dstEid,
            _getPeerOrRevert(_dstEid),
            _message,
            _options,
            _fee.lzTokenFee > 0
        ),
        _refundAddress
    );
```

## What It Does

`endpoint.send(...)` hands the message to the LayerZero Endpoint.

It sends:

```text
destination EID
trusted peer
message payload
execution options
fee mode
refund address
```

