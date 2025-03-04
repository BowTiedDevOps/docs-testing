# Get All Token's Prices

**Description:**

This endpoint returns the cached prices for all available tokens.



**Endpoint:**

```
GET /get-prices
```



**Headers:**

| Name      | Value Type | Possible Values | Description                           |
| --------- | ---------- | --------------- | ------------------------------------- |
| x-api-key | string     | -               | The API Key required to make requests |



**Response Codes:**

* **200**: Success, returns the prices for all tokens
* **404:** Prices not found
* **500**: Database error



**Response Data:**

```json
{
  "stx": 1.6824,
  "eth": 2444.8874,
  "btc": 62404.9681,
  "matic": 0.3622,
  "sol": 145.3679,
  "usdt": 0.9995,
  "usdc": 0.9997
}
```
