# Verify BNS Existence / Get Address BNS List

**Description:**

This endpoint verifies a BNS name or returns the BNS names associated with an address. Only 1 query parameter is required, giving both will default to verifying the BNS name.



**Endpoint:**

```
GET /verify-bns
```



**Query Parameters:**

| Name    | Value Type | Possible Values | Description                           |
| ------- | ---------- | --------------- | ------------------------------------- |
| bns     | string     | -               | The BNS name to verify                |
| address | string     | -               | The address to retrieve BNS names for |



**Headers:**

| Name      | Value Type | Possible Values | Description                           |
| --------- | ---------- | --------------- | ------------------------------------- |
| x-api-key | string     | -               | The API Key required to make requests |



**Response Codes:**

* **200**: Success, returns BNS information
* **400**: Missing or invalid parameter
* **404:** BNS or Address not found



**Response Data:**

```json
Address Query Parameter Used:
{
  "names": [
    "ubid.app"
  ]
}

BNS Query Parameter Used:
{
  "address": "SP2N1G991SE9JP4JF3427DZF7NNXG3XD8J0KCFH57",
  "blockchain": "stacks",
  "last_txid": "0x5243838c9e5bdd68eca1af3b17e0c5c0fa500a3d0a8a06d559b6d51c10bf7836",
  "status": "name-update",
  "zonefile_hash": "ba5d931414e7db41185abe96ff77a627e1bdcbbe",
  "expire_block": 169420,
  "zonefile": "$ORIGIN ubid.app\n$TTL 3600\nsr_mauro\tIN\tTXT\t\"owner=SP2A82GBXBK5XE807N6C5X0WF1XN3QYPBYKF7BEKR\" \"seqn=0\" \"parts=1\" \"zf0=JE9SSUdJTiBzcl9tYXVyby51YmlkLmFwcC4KJFRUTCAzNjAwCl9odHRwLl90Y3AJSU4JVVJJCTEwCTEJImh0dHBzOi8vZ2FpYS5oaXJvLnNvL2h1Yi8xS21IdUpuRnFiV1hicVlIaGpUVVZaV0gxdFBzYmN4UFduL3Byb2ZpbGUuanNvbiIKCg==\"\nkaream\tIN\tTXT\t\"owner=SP33XQ4FSHBDBERF4BSS3S56FTTP01Q4KMFC9EXE6\" \"seqn=0\" \"parts=1\" \"zf0=JE9SSUdJTiBrYXJlYW0udWJpZC5hcHAuCiRUVEwgMzYwMApfaHR0cC5fdGNwCUlOCVVSSQkxMAkxCSJodHRwczovL2dhaWEuaGlyby5zby9odWIvMThuSnlLWGY0cEpvYkVpVnFuWE51aU1OTVIyOU1VeDdHSy9wcm9maWxlLmpzb24iCgo=\"\n_http._tcp\tIN\tURI\t10\t1\t\"https://gaia.hiro.so/hub/1Pi5g3R79uavJeSgS5LHmVhaF6YXiovC9A/profile.json\"\n",
  "bns": "ubid.app"
}
```
