# Get Address Balances On A Given Network

**Description:**

This endpoint returns the balance and tokens of a specified address for a given blockchain network.



**Endpoint:**

```
GET /get-balances
```



**Query Parameters:**

| Name    | Value Type | Possible Values                   | Description                         |
| ------- | ---------- | --------------------------------- | ----------------------------------- |
| network | string     | stacks, ethereum, bitcoin, solana | The blockchain network to query     |
| address | string     | -                                 | The address to retrieve balance for |



**Headers:**

| Name      | Value Type | Possible Values | Description                           |
| --------- | ---------- | --------------- | ------------------------------------- |
| x-api-key | string     | -               | The API Key required to make requests |



**Response Codes:**

* **200**: Success, returns balances
* **400**: Missing or invalid parameters
* **404:** Balances not found
* **500**: Database error



**Response Data:**

```json
Stacks:
{
  "stx": {
    "balance": "1.06744",
    "total_sent": "28016.9",
    "total_received": "28098.560887",
    "total_fees_sent": "80.593447",
    "total_miner_rewards_received": "0",
    "lock_tx_id": "",
    "locked": "0",
    "lock_height": 0,
    "burnchain_lock_height": 0,
    "burnchain_unlock_height": 0,
    "total_balance": "1.06744",
    "balance_usd_value": "1.800451048"
  },
  "fungible_tokens": [
    {
      "balance": "1976",
      "total_sent": "0",
      "total_received": "1976",
      "name": "Bull",
      "symbol": "BULL",
      "total_supply": "100000000",
      "txid": "0xe53637aa4e2ff79934c1ad24270f8fa8b2fde415831d2bbc19275d27075c4e2f",
      "token_id": "SP1Q4E6971M7HJ6H8XXDSCAFJ96GEQ02RNN8S55ZZ.bull::BULL",
      "description": null,
      "token_uri": "ipfs://ipfs/bafkreiarvuvr23476z652gijncpns7kvpo7tyuu73reukxhkoywurs2rjq",
      "image_uri": null,
      "metadata": null
    },
    ...
  ],
  "non_fungible_tokens": [
    {
      "count": "1",
      "total_sent": "0",
      "total_received": "1",
      "token_uri": "https://nft-ad-1.aibtc.dev/aibtcdev-1.json",
      "metadata": {
        "sip": 16,
        "name": "aibtcdev-1",
        "description": "Hackers Uniting AI with Bitcoin. First Edition. Join us at https://aibtc.dev",
        "image": "https://nft-ad-1.aibtc.dev/aibtcdev-1.png",
        "cached_image": "https://assets.hiro.so/api/mainnet/token-metadata-api/SP97M6Z0T8MHKJ6NZE0GS6TRERCG3GW1WVJ4NVGT.aibtcdev-airdrop-1/1.png",
        "cached_thumbnail_image": "https://assets.hiro.so/api/mainnet/token-metadata-api/SP97M6Z0T8MHKJ6NZE0GS6TRERCG3GW1WVJ4NVGT.aibtcdev-airdrop-1/1-thumb.png",
        "attributes": [
          {
            "trait_type": "generation",
            "value": "first",
            "display_type": ""
          }
        ],
        "properties": {
          "category": "image",
          "collection": "AIBTC",
          "collection_image": "https://nft-ad-1.aibtc.dev/aibtcdev-1.png"
        }
      }
    },
    ...
  ],
  "address": "SPPBKX2EJHENTH2Z04H0S93AJZ8729DX86W55B89"
}



Solana:
{
  "sol": {
    "balance": "94.489877058",
    "balance_usd_value": "13735.7949991796382"
  },
  "tokens": [
    {
      "id": "5L9PnBs5TnhvL17An2hRrieavzhw93deWAMTv2EYFXZB",
      "native": false,
      "mint": "FLQ1LHNc5q12ENtUCW1T3BCW5R24obvNvtf7NBN9saRA",
      "amount": "81034778",
      "decimals": 0,
      "userInterfaceAmount": 81034778,
      "name": null,
      "symbol": null,
      "type": null,
      "image": null,
      "extensions": null
    },
    {
      "id": "6CKhtqvi5cn2HX3YDjCAd1PEqPyKwrqbdYao6kVEeGKX",
      "native": false,
      "mint": "F9CpWoyeBJfoRB8f2pBe2ZNPbPsEE76mWZWme3StsvHK",
      "amount": "100",
      "decimals": 6,
      "userInterfaceAmount": 0.0001,
      "name": "Pepe",
      "symbol": "PEPE",
      "type": "Fungible",
      "image": "https://shdw-drive.genesysgo.net/8XiSN28HJqb9czfsBYXsTkLtf4wgAupLpozEaUyA419K/pepecoin.png",
      "extensions": {
        "coingeckoId": "pepesol"
      }
    },
    ...
  ],
  "address": "GZctHpWXmsZC1YHACTGGcHhYxjdRqQvTpYkb9LMvxDib"
}

```
