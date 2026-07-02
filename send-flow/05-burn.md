# 05 - _burn(...)

## Function Code

```solidity
function _burn(address account, uint256 value) internal {
    if (account == address(0)) {
        revert ERC20InvalidSender(address(0));
    }
    _update(account, address(0), value);
}
```

## What It Does

`_burn(...)` burns tokens from `account`.

It:

```text
decreases account balance
decreases totalSupply
```

## Important Parts

```solidity
if (account == address(0)) {
    revert ERC20InvalidSender(address(0));
}
```

Prevents burning from the zero address.

```solidity
_update(account, address(0), value);
```

Moves tokens from `account` to `address(0)`, which means burn.

