# ink-brush-staking-contract

ink brush staking contract, following this tutorial: https://www.youtube.com/watch?v=JDua1vwBR5I

## Build Instructions

```bash
~/contracts % cargo contract build
```

**Currently fails with:**

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
   Compiling staking_contract v0.1.0 (/private/var/folders/9y/ny58jn152dzcqf036v5cb4nh0000gn/T/cargo-contract_nsgIzw)
error: `#[panic_handler]` function required, but not found

error: could not compile `staking_contract` due to previous error
ERROR: `"/Users/xxx/.rustup/toolchains/nightly-aarch64-apple-darwin/bin/cargo" "build" "--target=wasm32-unknown-unknown" "-Zbuild-std" "--no-default-features" "--release" "--target-dir=/Users/xxx/repos/ink-brush-test/staking_contract/contracts/target/ink" "--features" "ink/ink-debug"` failed with exit code: Some(101)
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