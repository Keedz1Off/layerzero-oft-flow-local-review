# 09 - _lzSend(...)

## Function Code

```solidity
function _lzSend(
    uint32 _dstEid,
    bytes memory _message,
    bytes memory _options,
    MessagingFee memory _fee,
    address _refundAddress
) internal virtual returns (MessagingReceipt memory receipt) {
    uint256 messageValue = _payNative(_fee.nativeFee);

    if (_fee.lzTokenFee > 0) _payLzToken(_fee.lzTokenFee);

    return
        endpoint.send{ value: messageValue }(
            MessagingParams(_dstEid, _getPeerOrRevert(_dstEid), _message, _options, _fee.lzTokenFee > 0),
            _refundAddress
        );
}
```

## What It Does

`_lzSend(...)` sends the built message to the LayerZero Endpoint.

It:

```text
pays native fee
optionally pays LZ token fee
calls endpoint.send(...)
```

## Invariants

```text
TODO: write main invariants here.
```

## Consequences

```text
TODO: write consequences here.
```

