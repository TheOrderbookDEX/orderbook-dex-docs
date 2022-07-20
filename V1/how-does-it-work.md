# How does **V1** work?

## The basics, explained in under 5 minutes

  * *The Orderbook* keeps a record of `total contracts placed` on a price point.

  * It also keeps a record of `total contracts filled`.

  * Each order keeps a record of the amount of `contracts placed before the order`.

  * If the `total contracts filled > contracts placed before the order`

    - The order has been **filled**.

    - The difference between the values indicates **how much** of it has been filled.

## Regarding canceling orders

  * For an order to be canceled, orders placed after it **must** also be updated to keep the system **consistent**.

  * Each order keeps track of the `previous order` and the `next order`.

    > This is what is commonly referred to as a `doubly linked list`.

  * When an order is canceled, it can be **deleted** and the `previous order` and the `next order` updated accordingly.

    > Search `doubly linked list deletion` for details on how this work.
    >
    > Deletion in a `doubly linked list` is **O(1)** and doesn't change the order of items.

  * This way other orders that wish to be canceled don't have to go through **all orders** after it, only the **remaining ones**.

    > Transversing a `doubly linked list` is still **O(n)**, but this way **n** can shrink.
    >
    > If orders start being canceled from the tail of the queue upwards, everyone eventually gets a chance to cancel at a reasonable gas cost.
