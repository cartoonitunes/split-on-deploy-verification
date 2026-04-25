# SplitOnDeploy Contract Verification

Bytecode verification proof for the `SplitOnDeploy` contract deployed from Vitalik Buterin's testing address.

This contract splits incoming ETH equally between two addresses on deployment, then the
deployed runtime is a minimal 12-byte always-revert stub (no callable functions).

## Instances

- `0xa2af18e8cbf42298fe5013e129104610fb17476a` — Block 2,353,701 (September 30, 2016)
- `0xe0a62fa7b2708bfd2f01c0e5e24080b011a5662b` — Block 2,533,297 (October 30, 2016)

Both addresses share identical bytecode.

## Verification

- **Compiler**: solc 0.4.4 (no optimizer)
- **Match**: Exact bytecode match

```
solc --bin SplitOnDeploy.sol
```

The constructor sends `msg.value / 2` to each of:
- `0x1Db3439a222C519ab44bb1144fC28167b4Fa6eE6` (Vitalik's deployer address)
- `0xd8dA6BF26964aF9D7eEd9e03E53415D37aA96045` (Vitalik's main address)

## Part of [Ethereum History](https://ethereumhistory.com)
