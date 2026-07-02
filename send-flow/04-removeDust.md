# 04 - _removeDust(...)

## Function Code

```solidity
function _removeDust(uint256 _amountLD) internal view virtual returns (uint256 amountLD) {
    return (_amountLD / decimalConversionRate) * decimalConversionRate;
}
```

## What It Does

`_removeDust(...)` rounds the amount down to a value that can be converted between local decimals and shared decimals.

Example:

```text
_amountLD = 123456789
decimalConversionRate = 1000

(123456789 / 1000) * 1000 = 123456000
```

The removed dust is:

```text
789
```

## Invariants

```text
TODO: write main invariants here.
```

## Consequences

```text
TODO: write consequences here.
```

