# ink-brush-staking-contract

ink brush staking contract, following this tutorial: https://www.youtube.com/watch?v=JDua1vwBR5I

## Build Instructions

```bash
cargo contract build
```

**Currently, this command fails with the following error:**

```bash
error[E0277]: the trait bound `openbrush::openbrush_contracts::psp22::Data: TypeInfo` is not satisfied
   --> /Users/xxx/repos/ink-brush-test/staking_contract/contracts/lib.rs:13:16
    |
13  |         psp22: psp22::Data
    |                ^^^^^^^^^^^ the trait `TypeInfo` is not implemented for `openbrush::openbrush_contracts::psp22::Data`
    |
    = help: the following other types implement trait `TypeInfo`:
              &T
              &mut T
              ()
              (A, B)
              (A, B, C)
              (A, B, C, D)
              (A, B, C, D, E)
              (A, B, C, D, E, F)
            and 65 others
note: required by a bound in `FieldBuilder::<MetaForm, N>::ty`
   --> /Users/xxx/.cargo/registry/src/github.com-1ecc6299db9ec823/scale-info-2.3.1/src/build.rs:458:13
    |
458 |         TY: TypeInfo + 'static + ?Sized,
    |             ^^^^^^^^ required by this bound in `FieldBuilder::<MetaForm, N>::ty`

error[E0277]: the trait bound `openbrush::openbrush_contracts::psp22::Data: StorageLayout` is not satisfied
  --> /Users/xxx/repos/ink-brush-test/staking_contract/contracts/lib.rs:10:5
   |
10 | /     #[derive(Storage, Default)]
11 | |     pub struct StakingContract {
12 | |         #[storage_field]
13 | |         psp22: psp22::Data
14 | |     }
   | |_____^ the trait `StorageLayout` is not implemented for `openbrush::openbrush_contracts::psp22::Data`
   |
   = help: the following other types implement trait `StorageLayout`:
             ()
             (A, B)
             (A, B, C)
             (A, B, C, D)
             (A, B, C, D, E)
             (A, B, C, D, E, F)
             (A, B, C, D, E, F, G)
             (A, B, C, D, E, F, G, H)
           and 62 others
   = note: this error originates in the derive macro `::ink::storage::traits::StorageLayout` (in Nightly builds, run with -Z macro-backtrace for more info)

error[E0277]: the trait bound `openbrush::openbrush_contracts::psp22::PSP22Error: TypeInfo` is not satisfied
    --> /Users/xxx/repos/ink-brush-test/staking_contract/contracts/lib.rs:4:1
     |
4    | #[openbrush::contract]
     | ^^^^^^^^^^^^^^^^^^^^^^ the trait `TypeInfo` is not implemented for `openbrush::openbrush_contracts::psp22::PSP22Error`
     |
     = help: the following other types implement trait `TypeInfo`:
               &T
               &mut T
               ()
               (A, B)
               (A, B, C)
               (A, B, C, D)
               (A, B, C, D, E)
               (A, B, C, D, E, F)
             and 65 others
     = note: required for `Result<(), openbrush::openbrush_contracts::psp22::PSP22Error>` to implement `TypeInfo`
     = note: 1 redundant requirement hidden
     = note: required for `Result<Result<(), openbrush::openbrush_contracts::psp22::PSP22Error>, LangError>` to implement `TypeInfo`
note: required by a bound in `TypeSpec::with_name_segs`
    --> /Users/xxx/.cargo/git/checkouts/ink-1add513eda8f5a89/4655a8b/crates/metadata/src/specs.rs:1004:12
     |
1004 |         T: TypeInfo + 'static,
     |            ^^^^^^^^ required by this bound in `TypeSpec::with_name_segs`
     = note: this error originates in the attribute macro `::ink::contract` (in Nightly builds, run with -Z macro-backtrace for more info)

For more information about this error, try `rustc --explain E0277`.
error: could not compile `staking_contract` due to 3 previous errors
ERROR: `"/Users/xxx/.rustup/toolchains/nightly-aarch64-apple-darwin/bin/cargo" "run" "--package" "metadata-gen" "--manifest-path=/private/var/folders/9y/ny58jn152dzcqf036v5cb4nh0000gn/T/cargo-contract_0KzP2j/Cargo.toml" "--target-dir=/Users/xxx/repos/ink-brush-test/staking_contract/contracts/target/ink" "--release" ""` failed with exit code: Some(101)
```
