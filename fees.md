# Fees

## How are fees collected

  * For orders that are executed immediately, e.g. a **V1 market order**, a percentage of the **tokens given** back to the order placer is taken as **fee**.

    > The fee is taken in a **different token** whether is a **buy or sell** order.

  * For orders that have to be claimed, e.g. a **V1 limit order**, the fee is taken when claiming a **filled order**.

    > The **fee** applied will be the one at the **time of claiming**.
    >
    > You should **claim** a filled order before the **fee changes**.

  * Canceling an order will return the **unfilled** amount without **no fees** applied.

## How is fee amount determined

  * *The Orderbook DEX* **Team Treasury** determines the fee according to **orderbook version**.

  * The fee **cannot** be set **above 0.5%**.

  * A fee **increase** must be scheduled **one week ahead** of time.
