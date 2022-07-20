# Client App

## Features

* Initially developed as a **web app**, it will be later on provided as a **desktop app**.

* It only uses **on-chain** data.

  > This means that it does not rely on any **centralized** data provider. While this does not compromise the **decentralized** nature of the system, it also means that it takes more time to boot up the market data.

* It's **distributed** both through decentralized and centralized means.

  > The app will be hosted on a **traditional web domain**, but the recommended way to access the app is through **decentralized distribution**, which will be eventually the sole way to access the app.

* For **UX reasons**, the app interacts with orderbooks through an ***Operator*** smart contract owned by the user.

  > Check [this page](operator.md) for details.

* The app has one **centralization issue** to keep in mind regarding the **upgradability** of the ***Operator*** smart contracts.

  > It was decided to do it this way because it was deemed preferable than pushing on **every user** the cost of upgrading the smart contract on **each version release**.
  >
  > Please read more about this on [this page](operator-logic.md).

## More info

* [The *Operator* smart contract](operator.md)

* [The *Operator Logic* upgrade scheme](operator-logic.md)
