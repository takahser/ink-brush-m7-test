# ink-brush-staking-contract

ink brush staking contract, following this tutorial: https://www.youtube.com/watch?v=JDua1vwBR5I

## Build Instructions

```bash
~/contracts % cargo contract build
```

**Currently passes:**

```bash
~/contracts % cargo contract build
warning: nothing to print.

To find dependencies that require specific target platforms, try to use option `--target all` first, and then narrow your search scope accordingly.
 [1/5] Building cargo project
    Updating git repository `https://github.com/paritytech/ink`
    Updating git repository `https://github.com/727-Ventures/openbrush-contracts`
    Updating crates.io index
    Updating git repository `https://github.com/727-ventures/pallet-assets-chain-extension`
    Updating git repository `https://github.com/727-Ventures/obce`
   Compiling staking_contract v0.1.0 (/private/var/folders/9y/ny58jn152dzcqf036v5cb4nh0000gn/T/cargo-contract_7uRWFZ)
    Finished release [optimized] target(s) in 1.22s
 [2/5] Post processing wasm file
 [3/5] Optimizing wasm file
 [4/5] Generating metadata
    Updating git repository `https://github.com/paritytech/ink`
    Updating crates.io index
    Updating git repository `https://github.com/727-Ventures/openbrush-contracts`
    Updating git repository `https://github.com/727-ventures/pallet-assets-chain-extension`
    Updating git repository `https://github.com/727-Ventures/obce`
   Compiling staking_contract v0.1.0 (/private/var/folders/9y/ny58jn152dzcqf036v5cb4nh0000gn/T/cargo-contract_4kUL1x)
   Compiling metadata-gen v0.1.0 (/private/var/folders/9y/ny58jn152dzcqf036v5cb4nh0000gn/T/cargo-contract_4kUL1x/.ink/metadata_gen)
    Finished release [optimized] target(s) in 1.95s
     Running `target/ink/release/metadata-gen ''`
 [5/5] Generating bundle

Original wasm size: 53.9K, Optimized: 24.3K

The contract was built in DEBUG mode.

Your contract artifacts are ready. You can find them in:
/Users/xxx/repos/ink-brush-test/staking_contract/contracts/target/ink

  - staking_contract.contract (code + metadata)
  - staking_contract.wasm (the contract's code)
  - metadata.json (the contract's metadata)
```

## Test instructions

```bash
~/contracts % cargo contract test
```

**Currently succeeds:**

```bash
~/contracts % cargo contract test 
 [1/1] Running tests
    Finished test [unoptimized + debuginfo] target(s) in 0.17s
     Running unittests lib.rs (target/debug/deps/staking_contract-e44a0ac9c40d5b65)

running 2 tests
test staking_contract::tests::constructor_works ... ok
test staking_contract::tests::transfer_works ... ok

test result: ok. 2 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s
```