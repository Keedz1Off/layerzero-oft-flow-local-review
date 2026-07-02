# 11 - _payLzToken(...)

## Function Code

```solidity
function _payLzToken(uint256 _lzTokenFee) internal virtual {
    address lzToken = endpoint.lzToken();

    if (lzToken == address(0)) revert LzTokenUnavailable();

    SafeERC20.safeTransferFrom(IERC20(lzToken), msg.sender, address(endpoint), _lzTokenFee);
}
```

## What It Does

`_payLzToken(...)` pays the LayerZero token fee.

Simple flow:

```text
get LZ token address
check it is not address(0)
transfer LZ token fee from user to endpoint
```

## Invariants

```text
TODO: write main invariants here.
```

## Consequences

```text
TODO: write consequences here.
```

