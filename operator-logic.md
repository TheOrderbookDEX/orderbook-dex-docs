# The *Operator Logic* upgrade scheme

## How does an *Operator* upgrade?

* On the release of a **new version**, a smart contract for the ***Operator Logic*** of that version is deployed.

* This ***Operator Logic*** smart contract is afterwards registered in the ***Operator Logic Registry***.

* When an ***Operator*** is then asked to do an operation on an ***Orderbook***, it first checks **the version** of that *Orderbook*.

* Then the ***Operator*** checks the ***Operator Logic Registry*** for the ***Operator Logic*** assigned to that version.

* Finally, the ***Operator*** forwards the operation to the ***Operator Logic***.

## Why is it done this way?

* The alternative would be to ask **every user** to upgrade their ***Operator*** on each new version.

* This would mean that **total gas cost** of upgrading the *Operators* would be **directly proportional** to the amount of users.

  > Instead, we decided that it would be preferable if there was **no extra gas cost** for the users on a new version.

* Steps can be taken to **mitigate** the centralization issues of using this upgrade scheme.

## What measures are taken against centralization?

* The ***Operator Logic Registry*** does not allow the ***Operator Logic*** of a version to change once it's set.

  > This means that once you checked that it's safe to use an ***Operator Logic*** for a specific ***Orderbook* version**, you don't have to worry about it being **changed** for a malicious one.

* The ***Operator Logic Registry*** is owned by a multi-sig smart contract.
