# 10 - _payNative(...)

## Function Code

```solidity
function _payNative(uint256 _nativeFee) internal virtual returns (uint256 nativeFee) {
    if (msg.value != _nativeFee) revert NotEnoughNative(msg.value);
    return _nativeFee;
}
```

## What It Does

`_payNative(...)` checks that the user paid the exact required native fee.

Important:

```text
msg.value is the native coin sent with the transaction.
_payNative(...) does not calculate the fee.
It only checks msg.value == _nativeFee.
```

