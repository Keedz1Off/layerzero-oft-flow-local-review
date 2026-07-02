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
1. The amountSentLD equal amountReceivedLD.

2. amountSentLD must be burned on the source chain.

3. amountReceivedLD must be encoded to create a message. 
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
   1. Enforced options must stay in the final options .

   2.  A user must not remove (delete) the enforced options.



```

## _lzSend(...)

```text
INVARIANT
1. Fee must be paid before the endpoint.send()

2. The message must be sent to the trusted contract

2. The message must be sent to the correct destinqation chain ( _dstEid ).
```



```

## endpoint.send(...)

```text
INVARIANT
endpoint.send(...) must receive the verifited message and options.

```
