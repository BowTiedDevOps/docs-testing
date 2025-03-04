# Get All Network's Fees

**Description:**

This endpoint returns the transaction fees for all available networks.



**Endpoint:**

```
GET /get-fees
```



**Headers:**

| Name      | Value Type | Possible Values | Description                           |
| --------- | ---------- | --------------- | ------------------------------------- |
| x-api-key | string     | -               | The API Key required to make requests |



**Response Codes:**

* **200**: Success, returns fee details for all networks
* **500**: Database error



**Response Data:**

```json
{
  "stacks": {
    "low": 0.033005,
    "medium": 0.450889,
    "high": 3.58
  },
  "etherum": {
    "low": null,
    "medium": null,
    "high": null
  },
  "bitcoin": {
    "low": null,
    "medium": null,
    "high": null
  },
  "polygon": {
    "low": null,
    "medium": null,
    "high": null
  },
  "solana": {
    "low": 0.000005,
    "medium": 0.00006403,
    "high": 0.00019208999999999999
  }
}
```
