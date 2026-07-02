# 05 - _credit(...)

## Function Code

```solidity
function _credit(
    address _to,
    uint256 _amountLD,
    uint32 /*_srcEid*/
) internal virtual returns (uint256 amountReceivedLD) {
    _mint(_to, _amountLD);
    return _amountLD;
}
```

## What It Does

`_credit(...)` credits/mints tokens on the destination chain.

Simple flow:

```text
decoded recipient
decoded amount
-> _mint(...)
```

## Invariants

```text
TODO: write main invariants here.
```

## Consequences

```text
TODO: write consequences here.
```

