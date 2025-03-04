# Get A Token's Price

**Description:**

This endpoint returns the cached price of a specified token.



**Endpoint:**

```
GET /get-price
```



**Query Parameters:**

| Name  | Value Type | Possible Values                       | Description                        |
| ----- | ---------- | ------------------------------------- | ---------------------------------- |
| token | string     | stx, eth, btc, matic, sol, usdt, usdc | The token to retrieve the price of |



**Headers:**

| Name      | Value Type | Possible Values | Description                           |
| --------- | ---------- | --------------- | ------------------------------------- |
| x-api-key | string     | -               | The API Key required to make requests |



**Response Codes:**

* **200**: Success, returns the price for the specified token
* **400**: Missing or invalid token parameter
* **404:** Prices not found
* **500**: Database error



**Response Data:**

```json
{
  "stx": 1.6824
}
```
