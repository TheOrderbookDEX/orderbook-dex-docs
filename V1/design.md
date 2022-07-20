# Why is **V1** designed the way it is?

## Design Philosophy

  * The first release of **V1** was designed with **readability** as a top priority.

    > The key here is to prioritize the ease of understanding of *The Orderbook's* logic.

  * **V1** was designed expecting that its core functions will be called **a lot**.

      - Therefore, optimizations favor reduction of gas for these functions.

        > This is why **V1** does not use **proxies** or **libraries** to reduce the cost of deploying a new orderbook.

  * Some optimizations were disregarded in an attempt to avoid **premature optimization**.

    > We had no way of knowing how **V1** would be used effectively, so there was no way of knowing what optimizations would actually be required.

  * For both **efficiency** and **security** reasons, V1 only has and will ever have the **minimal required** features.

    - If something can be solved **externally**, without adding extra code, it will be solved that way exclusively.

      > This is why **V1** only works and will ever work with **strictly standard** ERC20 tokens.
      >
      > Tokens that don't fit the requirement (e.g. fee-on-transfer or rebase tokens) have to be wrapped to work.

      > This is also why **V1** does not and will not provide orders as NFTs directly. It can be done by using a wrapper.

  * **Observer** (view) functions provide only the **internal** state, and do **no validity checks**, neither on input nor output data.

    - Consumers of the smart contract are expected to do both the high level interpretation of the data and the validity checking.

    - This way the consumer can be more efficient by avoiding redundant validity checks and storage access.

      > For other smart contracts we provide a library with all the high level functions that interpret the internal data of *The Orderbook*.
