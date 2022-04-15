# acceptsToken

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

Contract: [`JBPayoutRedemptionPaymentTerminal`](/api/contracts/or-abstract/jbpayoutredemptionpaymentterminal/README.md)​‌

Interface: [`IJBPaymentTerminal`](/api/interfaces/ijbpaymentterminal.md)

<Tabs>
<TabItem value="Step by step" label="Step by step">

**A flag indicating if this terminal accepts the specified token.**

### Definition

```
function acceptsToken(address _token) external view override returns (bool) { ... }
```

* Arguments:
  * `_token` is the token to check if this terminal accepts or not.
* The view function can be accessed externally by anyone.
* The view function does not alter state on the blockchain.
* The resulting function overrides a function definition from the [`IJBPaymentTerminal`](/api/interfaces/ijbpaymentterminal.md) interface.
* The function returns the flag.

### Body

1.  In order for this terminal to accept a token, it must match the single token that this terminal is for.

    ```
    return _token == token;
    ```

</TabItem>

<TabItem value="Code" label="Code">

```
/** 
  @notice
  A flag indicating if this terminal accepts the specified token.

  @param _token The token to check if this terminal accepts or not.

  @return The flag.
*/
function acceptsToken(address _token) external view override returns (bool) {
  return _token == token;
}
```

</TabItem>

<TabItem value="Bug bounty" label="Bug bounty">

| Category          | Description                                                                                                                            | Reward |
| ----------------- | -------------------------------------------------------------------------------------------------------------------------------------- | ------ |
| **Optimization**  | Help make this operation more efficient.                                                                                               | 0.5ETH |
| **Low severity**  | Identify a vulnerability in this operation that could lead to an inconvenience for a user of the protocol or for a protocol developer. | 1ETH   |
| **High severity** | Identify a vulnerability in this operation that could lead to data corruption or loss of funds.                                        | 5+ETH  |

</TabItem>
</Tabs>