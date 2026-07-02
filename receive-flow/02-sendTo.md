# 02 - sendTo(...)

## Function Code

```solidity
function sendTo(bytes calldata _msg) internal pure returns (bytes32) {
    return bytes32(_msg[0:SEND_TO_OFFSET]);
}
```

## What It Does

`sendTo(...)` reads the recipient from the message payload.

Payload layout:

```text
[recipient][amount][optional compose]
```

So `sendTo(...)` reads the first 32 bytes.

## Invariants

```text
TODO: write main invariants here.
```

## Consequences

```text
TODO: write consequences here.
```

