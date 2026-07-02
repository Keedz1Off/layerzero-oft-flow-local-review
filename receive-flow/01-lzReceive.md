# 01 - _lzReceive(...)

## Function Code

```solidity
function _lzReceive(
    Origin calldata _origin,
    bytes32 _guid,
    bytes calldata _message,
    address /*_executor*/,
    bytes calldata /*_extraData*/
) internal virtual override {
    address toAddress = _message.sendTo().bytes32ToAddress();

    uint256 amountToCreditLD = _toLD(_message.amountSD());

    uint256 amountReceivedLD = _credit(toAddress, amountToCreditLD, _origin.srcEid);

    if (_message.isComposed()) {
        bytes memory composeMsg = OFTComposeMsgCodec.encode(
            _origin.nonce,
            _origin.srcEid,
            amountReceivedLD,
            _message.composeMsg()
        );

        endpoint.sendCompose(toAddress, _guid, 0, composeMsg);
    }

    emit OFTReceived(_guid, _origin.srcEid, toAddress, amountReceivedLD);
}
```

## What It Does

`_lzReceive(...)` is the destination-side receive/finalize function.

It:

```text
decodes recipient
decodes amount
credits/mints tokens
optionally sends compose message
emits receive event
```

