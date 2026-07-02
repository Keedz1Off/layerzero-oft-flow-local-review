# 03 - amountSD(...)

## Function Code

```solidity
function amountSD(bytes calldata _msg) internal pure returns (uint64) {
    return uint64(bytes8(_msg[SEND_TO_OFFSET:AMOUNT_OFFSET]));
}
```

## What It Does

`amountSD(...)` reads the amount from the message payload in shared decimals.

Payload layout:

```text
[recipient: 32 bytes][amountSD: 8 bytes][optional compose]
```

## Invariants

```text
TODO: write main invariants here.
```

## Consequences

```text
TODO: write consequences here.
```

