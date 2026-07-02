# Send Flow Break Think

## send(...)

```text
INVARIANT
1. The message must be sent to the trusted contract on destination chain.

2. The encoded recipient must be the correct recipient.

3. The encoded amount must match the burned amount.

4. Burn must happen before the message.


```

## _debit(...)

```text
INVARIANT


```

## _debitView(...)

```text
INVARIANT

```

## _removeDust(...)

```text
INVARIANT

```

## _burn(...)

```text
INVARIANT
1. Burn must be executed before the message.

2. Burned amount must match the encoded message.

3. Tokens must be burned from the correct account.
```

## _buildMsgAndOptions(...)

```text
INVARIANT
1. The message must encode the correct amount and recipient (receiver)

2. msgType must be SEND_AND_CALL if composeMsg exits.

3. Final options must include all enforced options.
```

## OFTMsgCodec.encode(...)

```text
INVARIANT

```

## combineOptions(...)

```text
INVARIANT

```

## _lzSend(...)

```text
INVARIANT
1. Fee must be paid before the endpoint.send()

2. The message must be sent to the trusted contract

2. The message must be sent to the correct destinqation chain ( _dstEid ).
```

## _payNative(...)

```text
INVARIANT

```

## _payLzToken(...)

```text
INVARIANT

```

## endpoint.send(...)

```text
INVARIANT

```
