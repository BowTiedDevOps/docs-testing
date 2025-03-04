# Get Address Transactions On A Given Network

**Description:**

This endpoint returns the transaction history for a given address and network.



**Endpoint:**

```
GET /get-transactions
```



**Query Parameters:**

| Name    | Value Type | Possible Values                   | Description                                       |
| ------- | ---------- | --------------------------------- | ------------------------------------------------- |
| network | string     | stacks, ethereum, bitcoin, solana | The blockchain network to query                   |
| address | string     | -                                 | The address to retrieve transactions for          |
| limit   | number     | -                                 | The number of transactions to return (default 30) |
| offset  | number     | -                                 | The number of transactions to skip (default to 0) |



**Headers:**

| Name      | Value Type | Possible Values | Description                           |
| --------- | ---------- | --------------- | ------------------------------------- |
| x-api-key | string     | -               | The API Key required to make requests |



**Response Codes:**

* **200**: Success, returns transactions
* **400**: Missing or invalid parameters
* **404:** Transactions not found
* **500**: Database error



**Response Data:**

```json
{
  "transactions": [
    {
      "txid": "0x47ac7f5138d120dcf2b3ba530e149e27656df590acf6ae8e578db4a523602f14",
      "nonce": 848,
      "fee_rate": "2497",
      "block_time": 1728655560,
      "block_height": 169406,
      "sender": "SP1XKHXQFEQXZ8ZFKSRG7J393YE73ZN89THVGC9C2",
      "recipient": null,
      "amount": null,
      "tx_type": "contract_call",
      "contract_id": "SP1QBKVTKP2DG8BGHQQD3KG6EBWWCB6V4X5NXQRYR.eth-thcam-stxcity",
      "contract_function": "transfer",
      "status": "success"
    },
    ...
  ],
  "network": "stacks"
}
```
