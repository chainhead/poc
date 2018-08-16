# Introduction

A simple PoC for loan syndication. The scope of this PoC is defined as:

> Loan syndication between a consortium of banks to put the underlying collateral on block-chain to share that information between the consortium to avoid frauds. Leverage the smart contracts to build this prototype.

- [Introduction](#introduction)
  - [Background](#background)
  - [Decentralized consensus](#decentralized-consensus)
  - [Solution](#solution)

## Background

Loan syndication is defined at [Investopedia](https://www.investopedia.com/terms/l/loansyndication.asp) as follows:

>Loan syndication is the process of involving a group of lenders to fund various portions of a loan for a single borrower. Loan syndication most often occurs when a borrower requires an amount too large for a single lender to provide or when the loan is outside the scope of a lender's risk exposure levels. Thus, multiple lenders form a syndicate to provide the borrower with the requested capital.

In this PoC, we show how, a given collateral is not pledged multiple times within a consortium of lenders or even across consortia. To jump into the demo, go to **Solution**.

## Decentralized consensus

The problem of _consensus_ has the following characteristics:

- Two or more parties.
- Parameter of interest.
- Central custodian of the value of the parameter of interest.
- Consensus _enforced_ by the custodian.

With _decentralized consensus_, the characteristics can be redefined as:

- Two or more parties.
- Parameter of interest.
- Network of peers store the value of parameter of interest.
- Consensus arrived via algorithms executed on nodes of a network.

Therefore, we re-write the scope of PoC in terms of decentralized consensus as follows:

- Parties: banks of a consortium and loan applicant.
- Parameter of interest: collateral identifier.
- Value of parameter of interest: status of collateral - pledged or not - for a loan in the past.
- Consensus: Proof of Authority consensus.

## Solution

> This demo saves _only_ the identifiers on the blockchain. The mechanism to generate and derefernce the identifiers is considered **out of scope**. Similarly, it is assumed that, all participants have agreed to common identifiers of loans, collaterals, consortia or others. It is a good practice to save only identifiers or references to actual data on the blockchain. On one hand, this makes the blockchain _light weight_ and on the other, a certain level of privacy is maintained.

There are two ways to see this PoC in action.

1. ![Quick start](doc/quickstart.md) - a simple demonstration of the Smart Contract without focussing much on underlying infra-structure.
2. ![AWS infra-structure](doc/awsinfra.md) - an underlying infra-structure on Amazon Web Services (AWS), on to which the Smart Contract is deployed, is described.

In both of the demos, the following are covered:

1. Deployment of contract.
2. Create a new consortium.
3. Read the members of the consortium created in 2.
4. Read the leader of the consortium created in 2.
5. Create a new loan with the consortium (created in 2) with a collateral.
6. Create a new loan with the consortium (created in 2) with same collateral as used in 5.