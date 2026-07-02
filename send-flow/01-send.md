# 01 - send(...)

## Function Code

```solidity
function send(
    SendParam calldata _sendParam,
    MessagingFee calldata _fee,
    address _refundAddress
) external payable virtual returns (MessagingReceipt memory msgReceipt, OFTReceipt memory oftReceipt) {
    (uint256 amountSentLD, uint256 amountReceivedLD) = _debit(
        msg.sender,
        _sendParam.amountLD,
        _sendParam.minAmountLD,
        _sendParam.dstEid
    );

    (bytes memory message, bytes memory options) = _buildMsgAndOptions(_sendParam, amountReceivedLD);

    msgReceipt = _lzSend(_sendParam.dstEid, message, options, _fee, _refundAddress);

    oftReceipt = OFTReceipt(amountSentLD, amountReceivedLD);

    emit OFTSent(msgReceipt.guid, _sendParam.dstEid, msg.sender, amountSentLD, amountReceivedLD);
}
```

## What It Does

`send(...)` is the main source-chain entry point.

It:

```text
debits/burns tokens
builds the LayerZero message
sends the message through LayerZero
returns receipts
```

## Important Parts

```solidity
(uint256 amountSentLD, uint256 amountReceivedLD) = _debit(...);
```

Calculates and burns/debits the source-chain amount.

```solidity
(bytes memory message, bytes memory options) = _buildMsgAndOptions(...);
```

Builds the payload and execution options.

```solidity
msgReceipt = _lzSend(...);
```

Sends the message to the LayerZero Endpoint.

## Invariants

```text
TODO: write main invariants here.
```

## Consequences

```text
TODO: write consequences here.
```

