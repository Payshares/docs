---
title: Fees
---

The Payshares network requires small [fees on transactions](#transaction-fee) and [minimum balances on accounts](#minimum-account-balance) in order to prevent people from overwhelming the network and to aid in prioritization.

There are two special values used to calculate fees:

1. The **base fee** (currently 100 stroops) is used in transaction fees.
2. The **base reserve** (currently 0.5 XPS) is used in minimum account balances.


## Transaction Fee

The fee for a transaction is the number of operations the transaction contains multiplied by the **base fee**, which is **100 stroops** (0.00001 XPS).

```math-formula
([# of operations] * [base fee])
```

For example, a transaction that allows trust on an account’s trustline *(operation 1)* and sends a payment to that account *(operation 2)* would have a fee of $$2 * [base fee] = 200 stroops$$.

Payshares deducts the entire fee from the transaction’s [source account](./transactions.md#source-account), regardless of which accounts are involved in each operation or who signed the transaction.


### Transaction Limits

Each Payshares node usually limits the number of transactions that it will propose to the network when a ledger closes. If too many transactions are submitted, nodes propose the transactions with the highest fees for the ledger’s transaction set. Transactions that aren’t included are held for a future ledger, when fewer transactions are waiting.

See [transaction life cycle](./transactions.md#life-cycle) for more information.

## Fee Pool

The fee pool is the lot of stakks collected from [transaction fees](./fees.md#transaction-fee).

Payshares does not retain these stakks. They are distributed in the weekly process of [inflation voting](./inflation.md). 

If there are any unallocated stakks after the vote, those stakks return to the fee pool for dispersal in the next round. 

## Minimum Account Balance

All Payshares accounts must maintain a minimum balance of stakks. Any transaction that would reduce an account's balance to less than the minimum will be rejected with an `INSUFFICIENT_BALANCE` error.

The minimum balance is calculated using the **base reserve,** which is **0.5 XPS**:

```math-formula
(2 + [# of entries]) * [base reserve]
```

The minimum balance for a basic account is $$2 * [base reserve]$$. Each additional entry costs the base reserve. Entries include:

- Trustlines
- Offers
- Signers
- Data entries

For example, an account with 1 trustline and 2 offers would have a minimum balance of $$(2 + 3) * [base reserve] = 2.5 XPS$$.


## Fee Changes

The **base reserve** and **base fee** can change, but should not do so more than once every several years. For the most part, you can think of them as fixed values. When they are changed, the change works by the same consensus process as any transaction. For details, see [versioning](https://www.payshares.org/developers/guides/concepts/versioning.html).

You can look up the current fees by [checking the details of the latest ledger](../../horizon/reference/endpoints/ledgers-single.md).
