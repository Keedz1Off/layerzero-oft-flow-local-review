# 06 - Compose Path

## Function Code

```solidity
if (_message.isComposed()) {
    bytes memory composeMsg = OFTComposeMsgCodec.encode(
        _origin.nonce,
        _origin.srcEid,
        amountReceivedLD,
        _message.composeMsg()
    );

    endpoint.sendCompose(toAddress, _guid, 0, composeMsg);
}
```

## What It Does

The compose path runs only when the message contains compose data.

It:

```text
checks if compose exists
builds compose message
sends compose through endpoint.sendCompose(...)
```

## Invariants

```text
TODO: write main invariants here.
```

## Consequences

```text
TODO: write consequences here.
```

