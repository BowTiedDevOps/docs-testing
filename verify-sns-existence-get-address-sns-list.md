# Verify SNS Existence / Get Address SNS List

**Description:**

This endpoint verifies an SNS name or returns the SNS names associated with an address. Only 1 query parameter is required, giving both will default to verifying the BNS name.



**Endpoint:**

```
GET /verify-sns
```



**Query Parameters:**

| Name    | Value Type | Possible Values | Description                           |
| ------- | ---------- | --------------- | ------------------------------------- |
| sns     | string     | -               | The SNS name to verify                |
| address | string     | -               | The address to retrieve SNS names for |



**Headers:**

| Name      | Value Type | Possible Values | Description                           |
| --------- | ---------- | --------------- | ------------------------------------- |
| x-api-key | string     | -               | The API Key required to make requests |



**Response Codes:**

* **200**: Success, returns SNS information
* **400**: Missing or invalid parameters
* **404:** SNS or Address not found



**Response Data:**

```json
Address Query Parameter Used:
{
  "names": [
    "materialfuture"
  ]
}


SNS Query Parameter Used:
{
  "domain_name": "materialfuture",
  "address": "DGZGMTbpah4BhyrQbFwiLhRkkHRZrvbWoSPAKRTFAMbJ",
  "id": "6d6174657269616c667574757265"
}
```
