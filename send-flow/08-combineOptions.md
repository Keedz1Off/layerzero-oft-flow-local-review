# 08 - combineOptions(...)

## Function Code

```solidity
function combineOptions(
    uint32 _eid,
    uint16 _msgType,
    bytes calldata _extraOptions
) public view virtual returns (bytes memory) {
    bytes memory enforced = enforcedOptions[_eid][_msgType];

    if (enforced.length == 0) return _extraOptions;

    if (_extraOptions.length == 0) return enforced;

    if (_extraOptions.length >= 2) {
        _assertOptionsType3(_extraOptions);
        return bytes.concat(enforced, _extraOptions[2:]);
    }

    revert InvalidOptions(_extraOptions);
}
```

## What It Does

`combineOptions(...)` combines required execution options with user-provided extra options.

Simple idea:

```text
enforcedOptions + extraOptions = final options
```

If both options exist, the second TYPE_3 header is removed:

```text
enforced:     [TYPE_3][required options]
extraOptions: [TYPE_3][user options]
final:        [TYPE_3][required options][user options]
```

## Invariants

```text
TODO: write main invariants here.
```

## Consequences

```text
TODO: write consequences here.
```

