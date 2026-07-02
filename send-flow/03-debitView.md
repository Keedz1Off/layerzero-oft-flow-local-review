# 03 - _debitView(...)

## Function Code

```solidity
function _debitView(
    uint256 _amountLD,
    uint256 _minAmountLD,
    uint32 /*_dstEid*/
) internal view virtual returns (uint256 amountSentLD, uint256 amountReceivedLD) {
    amountSentLD = _removeDust(_amountLD);
    amountReceivedLD = amountSentLD;

    if (amountReceivedLD < _minAmountLD) {
        revert SlippageExceeded(amountReceivedLD, _minAmountLD);
    }
}
```

## What It Does

`_debitView(...)` calculates the amount before burn/debit.

It:

```text
removes dust
sets amountSentLD
sets amountReceivedLD
checks minimum amount
```

## Important Parts

```solidity
amountSentLD = _removeDust(_amountLD);
```

Removes the part that cannot be represented safely in shared decimals.

```solidity
amountReceivedLD = amountSentLD;
```

In the basic OFT model, sent amount and received amount are the same.

```solidity
if (amountReceivedLD < _minAmountLD) revert SlippageExceeded(...);
```

Protects the user from receiving less than expected.

## Invariants

```text
TODO: write main invariants here.
```

## Consequences

```text
TODO: write consequences here.
```

