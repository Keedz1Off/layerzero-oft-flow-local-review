# 07 - OFTMsgCodec.encode(...)

## Function Code

```solidity
function encode(
    bytes32 _sendTo,
    uint64 _amountShared,
    bytes memory _composeMsg
) internal view returns (bytes memory _msg, bool hasCompose) {
    hasCompose = _composeMsg.length > 0;

    _msg = hasCompose
        ? abi.encodePacked(_sendTo, _amountShared, addressToBytes32(msg.sender), _composeMsg)
        : abi.encodePacked(_sendTo, _amountShared);
}
```

## What It Does

`encode(...)` creates the message payload.

Without compose:

```text
[recipient][amount]
```

With compose:

```text
[recipient][amount][compose sender][composeMsg]
```

## Invariants

```text
TODO: write main invariants here.
```

## Consequences

```text
TODO: write consequences here.
```

