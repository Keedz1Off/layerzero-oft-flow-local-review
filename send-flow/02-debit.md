# 02 - _debit(...)

## Function Code

```solidity
function _debit(
    address _from,
    uint256 _amountLD,
    uint256 _minAmountLD,
    uint32 _dstEid
) internal virtual returns (uint256 amountSentLD, uint256 amountReceivedLD) {
    (amountSentLD, amountReceivedLD) = _debitView(_amountLD, _minAmountLD, _dstEid);
    _burn(_from, amountSentLD);
}
```

## What It Does

`_debit(...)` prepares the source-chain token debit.

It:

```text
calculates the amount
burns/debits tokens from _from
```

## Important Parts

```solidity
(amountSentLD, amountReceivedLD) = _debitView(...);
```

Only calculates the amount.

```solidity
_burn(_from, amountSentLD);
```

Actually burns the source-chain tokens.

