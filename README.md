
<img width="1983" height="793" alt="image" src="https://github.com/user-attachments/assets/af35f126-f541-49c5-a410-9c8c71c6476d" />



# LayerZero OFT Flow Local Review

This repository is my local review of the LayerZero OFT flow.

The goal of this repository is to document and understand the full token flow:

```text
source-chain debit/burn
-> message encoding
-> LayerZero endpoint send
-> message delivery
-> destination-chain receive
-> credit/mint
```

My review method:

```text
Understand the flow
-> write function notes
-> fill Break Think manually
```

## Repository Structure

```text
send-flow/
  01-send.md
  02-debit.md
  03-debitView.md
  04-removeDust.md
  05-burn.md
  06-buildMsgAndOptions.md
  07-OFTMsgCodec-encode.md
  08-combineOptions.md
  09-lzSend.md
  10-payNative.md
  11-payLzToken.md
  12-endpoint-send.md

receive-flow/
  01-lzReceive.md
  02-sendTo.md
  03-amountSD.md
  04-toLD.md
  05-credit.md
  06-compose.md

break-think/
  README.md
  send-break-think.md
  receive-break-think.md
```

## Main Flow

```text
send(...)
├── _debit(...)
│   ├── _debitView(...)
│   │   └── _removeDust(...)
│   └── _burn(...)
├── _buildMsgAndOptions(...)
│   ├── OFTMsgCodec.encode(...)
│   ├── combineOptions(...)
│   └── msgInspector.inspect(...)
└── _lzSend(...)
    ├── _payNative(...)
    ├── _payLzToken(...)
    └── endpoint.send(...)

LayerZero delivery

_lzReceive(...)
├── sendTo()
├── amountSD()
├── _toLD(...)
├── _credit(...)
└── optional compose path
```

## Break Think

The `break-think/` folder contains empty invariant templates.

I will fill these manually while reviewing each function.

