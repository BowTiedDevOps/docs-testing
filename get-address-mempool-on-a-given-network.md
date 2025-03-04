# Get Address Mempool On A Given Network

**Description:**

This endpoint returns the mempool transactions for a specified address and network.



**Endpoint:**

```
GET /get-mempool
```



**Query Parameters:**

| Name    | Value Type | Possible Values                   | Description                                      |
| ------- | ---------- | --------------------------------- | ------------------------------------------------ |
| network | string     | stacks, ethereum, bitcoin, solana | The blockchain network to query                  |
| address | string     | -                                 | The address to retrieve mempool transactions for |



**Headers:**

| Name      | Value Type | Possible Values | Description                           |
| --------- | ---------- | --------------- | ------------------------------------- |
| x-api-key | string     | -               | The API Key required to make requests |



**Response Codes:**

* **200**: Success, returns mempool transactions
* **400**: Missing or invalid parameters
* **404:** Mempool transactions not found
* **500**: Database error



**Response Data:**

```json
{
  "transactions": [
    {
      "txid": "0xd55042ef89ba9e877a6dabfe8c23be46bdd5de5dbbd68d13a19d523f689d7273",
      "nonce": 14,
      "fee_rate": "100000",
      "sender": "SP30QA39W8S4JKS9R2TCBQZQ6S19E659B5HAEN72A",
      "recipient": null,
      "amount": null,
      "tx_type": "contract_call",
      "contract_id": "SPW2CWKC61DTT1PBD6V0R7P81V5RJ2DX3FYSE8YK.alien-poop-stxcity-dex",
      "contract_function": "buy"
    },
    ...
  ],
  "network": "stacks"
}
```
