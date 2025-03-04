# Get A Network's Fee

**Description:**

This endpoint returns the cached transaction fees for a specified network.



**Endpoint:**

```
GET /get-fee
```



**Query Parameters:**

| Name    | Value Type | Possible Values                            | Description                                 |
| ------- | ---------- | ------------------------------------------ | ------------------------------------------- |
| network | string     | stacks, ethereum, bitcoin, polygon, solana | The blockchain network to retrieve fees for |



**Headers:**

| Name      | Value Type | Possible Values | Description                           |
| --------- | ---------- | --------------- | ------------------------------------- |
| x-api-key | string     | -               | The API Key required to make requests |



**Response Codes:**

* **200**: Success, returns the fee details
* **400**: Missing or invalid network parameter
* **404:** Network not found
* **500**: Database error



**Response Data:**

```json
{
  "network": "stacks",
  "low_priority": 0.033005,
  "medium_priority": 0.450889,
  "high_priority": 3.58
}
```
