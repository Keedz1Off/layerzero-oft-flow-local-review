# 04 - _toLD(...)

## Function Code

```solidity
function _toLD(uint64 _amountSD) internal view virtual returns (uint256 amountLD) {
    return _amountSD * decimalConversionRate;
}
```

## What It Does

`_toLD(...)` converts shared decimals amount into local decimals amount.

Example:

```text
sharedDecimals = 6
localDecimals = 18
decimalConversionRate = 10 ** 12

amountSD = 1,000,000
amountLD = 1,000,000 * 10 ** 12
amountLD = 1 token with 18 decimals
```

## Invariants

```text
TODO: write main invariants here.
```

## Consequences

```text
TODO: write consequences here.
```

