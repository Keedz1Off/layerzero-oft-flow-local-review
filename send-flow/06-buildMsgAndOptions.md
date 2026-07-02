# 06 - _buildMsgAndOptions(...)

## Function Code

```solidity
function _buildMsgAndOptions(
    SendParam calldata _sendParam,
    uint256 _amountLD
) internal view virtual returns (bytes memory message, bytes memory options) {
    bool hasCompose;
    (message, hasCompose) = OFTMsgCodec.encode(
        _sendParam.to,
        _toSD(_amountLD),
        _sendParam.composeMsg
    );

    uint16 msgType = hasCompose ? SEND_AND_CALL : SEND;

    options = combineOptions(_sendParam.dstEid, msgType, _sendParam.extraOptions);

    if (msgInspector != address(0)) IOAppMsgInspector(msgInspector).inspect(message, options);
}
```

## What It Does

`_buildMsgAndOptions(...)` builds the LayerZero message payload and execution options.

It:

```text
encodes recipient and amount
checks whether compose exists
selects SEND or SEND_AND_CALL
combines options
optionally runs msgInspector
```

## Invariants

```text
TODO: write main invariants here.
```

## Consequences

```text
TODO: write consequences here.
```

