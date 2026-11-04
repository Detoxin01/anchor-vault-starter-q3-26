# Anchor Vault Starter — Completed

A learning implementation of a SOL vault program built with Anchor during the TURBIN3 Builders Cohort Q4 2026, Week 2 Day 2.

> This project is based on the original starter repository by `moses7054`: [anchor_vault_starter_q3_26](https://github.com/moses7054/anchor_vault_starter_q3_26). The original repository is the source for the starter structure and initial deposit implementation; this copy completes the withdrawal and close flows and enables their tests.

## What it does

- Initializes a user-specific state PDA and a system-owned vault PDA.
- Deposits SOL into the vault using a System Program transfer CPI.
- Withdraws SOL after checking that the request is positive and does not exceed the spendable balance. The rent-exempt reserve remains in the vault, and the PDA signs the CPI using its seeds and stored bump.
- Closes the state PDA with Anchor's `close` constraint and drains the vault PDA to the user with a signed System Program transfer, returning its remaining lamports.

## Project layout

- `programs/q3_26_vault/src/instructions/initialize.rs` — creates the state PDA and funds the vault's rent reserve.
- `programs/q3_26_vault/src/instructions/deposit.rs` — deposits SOL from the user.
- `programs/q3_26_vault/src/instructions/withdraw.rs` — validates and withdraws the spendable balance.
- `programs/q3_26_vault/src/instructions/close.rs` — closes the state account and drains the vault.
- `programs/q3_26_vault/tests/test_initialize.rs` — LiteSVM integration test for initialize, deposit, withdraw, and close.

## Run the tests

The Rust version is pinned in `rust-toolchain.toml`. From the workspace root, run:

```bash
ANCHOR_BUILD_SBF_ARCH=v0 anchor test
```

The `v0` build target is used for this starter's LiteSVM 0.10 test dependency. The integration test checks the deposit and withdrawal balance changes and verifies that both the vault state account and vault balance are cleared at closure.

### Test result

Both Rust tests passed: the program ID unit test and the LiteSVM integration test.

# Anchor Vault Starter — Completed

A learning implementation of a SOL vault program built with Anchor during the TURBIN3 Builders Cohort Q4 2026, Week 2 Day 2.

> This project is based on the original starter repository by `moses7054`: [anchor_vault_starter_q3_26](https://github.com/moses7054/anchor_vault_starter_q3_26). The original repository is the source for the starter structure and initial deposit implementation; this copy completes the withdrawal and close flows and enables their tests.

## What it does

- Initializes a user-specific state PDA and a system-owned vault PDA.
- Deposits SOL into the vault using a System Program transfer CPI.
- Withdraws SOL after checking that the request is positive and does not exceed the spendable balance. The rent-exempt reserve remains in the vault, and the PDA signs the CPI using its seeds and stored bump.
- Closes the state PDA with Anchor's `close` constraint and drains the vault PDA to the user with a signed System Program transfer, returning its remaining lamports.

## Project layout

- `programs/q3_26_vault/src/instructions/initialize.rs` — creates the state PDA and funds the vault's rent reserve.
- `programs/q3_26_vault/src/instructions/deposit.rs` — deposits SOL from the user.
- `programs/q3_26_vault/src/instructions/withdraw.rs` — validates and withdraws the spendable balance.
- `programs/q3_26_vault/src/instructions/close.rs` — closes the state account and drains the vault.
- `programs/q3_26_vault/tests/test_initialize.rs` — LiteSVM integration test for initialize, deposit, withdraw, and close.

## Run the tests

The Rust version is pinned in `rust-toolchain.toml`. From the workspace root, run:

```bash
ANCHOR_BUILD_SBF_ARCH=v0 anchor test
```

The `v0` build target is used for this starter's LiteSVM 0.10 test dependency. The integration test checks the deposit and withdrawal balance changes and verifies that both the vault state account and vault balance are cleared at closure.

### Test result

Both Rust tests passed: the program ID unit test and the LiteSVM integration test.

<img width="1920" height="570" alt="output" src="https://github.com/user-attachments/assets/9c27e551-8cba-40b2-abee-e9294ff0b469" />


## Acknowledgment

Original starter: [https://github.com/moses7054/anchor_vault_starter_q3_26](https://github.com/moses7054/anchor_vault_starter_q3_26)

This repository is a cohort learning exercise based on that starter, with the withdrawal and close functionality completed and tested.



## Acknowledgment

Original starter: [https://github.com/moses7054/anchor_vault_starter_q3_26](https://github.com/moses7054/anchor_vault_starter_q3_26)

This repository is a cohort learning exercise based on that starter, with the withdrawal and close functionality completed and tested.
