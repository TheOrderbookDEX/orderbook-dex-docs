# The *Operator* smart contract

## Why is it used?

* The ***Orderbook*** smart contracts are not designed with **end user experience** in mind, as they are meant to also be used by **other smart contracts**.

* Particularly a transaction to place a limit order **close to market** might fail because the market moved.

* There is also the issue of **handling token approvals**.

  > We **rather not** make the user give **full access** of their funds to the orderbook smart contract, as this is considered a **poor practice** regarding security.

* Finally it helps give **proper feedback** of the result of an operation to the user.

  > EVM based chains are particularly **unreliable** when trying to obtain the **reason** why a transaction **failed**.
  >
  > The **Operator** helps exposing this info to the user.

## What does it do?

* The *Operator* acts as a **wallet** for the funds to be traded in *The Orderbook DEX* ecosystem.

  > Keep in mind that the Operator is a smart contract owned **solely** by the user.

* The *Operator* handles the required **token approvals** for each operation.

  > So there is no need to give any **permissions** to spend tokens.

* An operation to place a **limit order** will be filled through a **market order** if the market **moved**.

## Further considerations

* Keep in mind the ***Operator*** smart contract is esentially a **proxy**, and a malicious ***Operator Logic*** will be able to do **anything** with the funds held by the *Operator*.

  > Therefore, **do not use** a newly released version of an *Orderbook* until you have **checked** that it's **safe to use**.

* **Please read** about the ***Operator Logic*** upgrade scheme [here](operator-logic.md).
