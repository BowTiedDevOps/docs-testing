# Clarity Keywords

### block-height <a href="#block-height" id="block-height"></a>

{% hint style="info" %}
The Nakamoto hard fork will introduce a few new Clarity keywords. It's important to note that even with the new [block production mechanism](../concepts/block-production/), the `block-height` keyword behavior will not change. It will simply correspond to the current tenure height. This means any Clarity contracts using this keyword will be backwards compatible after the Nakamoto Upgrade.
{% endhint %}

Introduced in: Clarity 1

Removed in: Clarity 2

**Output: `uint`**

**Description:**

Returns the current block height of the Stacks blockchain in Clarity 1 and 2.
Upon activation of epoch 3.0, `block-height` will return the same value as `tenure-height`.
In Clarity 3, `block-height` is removed and has been replaced with `stacks-block-height`.

**Example:**

```
(> block-height u1000) ;; returns true if the current block-height has passed 1000 blocks.
```

### burn-block-height <a href="#burn-block-height" id="burn-block-height"></a>

{% hint style="warning" %}
There is a bug in Clarity 3 when `burn-block-height` is used within an `at-block` expression. Normally, keywords executed within an `at-block` expression will return the data for that specified block. This bug causes `burn-block-height` to always return the burn block at the current chain tip, even within an `at-block` expression. This behavior affects any Clarity 3 contracts and will be fixed in a future hard fork.
{% endhint %}

Introduced in: Clarity 1

**Output: `uint`**

**Description:**

Returns the current block height of the underlying burn blockchain.

**Example:**

```
(> burn-block-height u832000) ;; returns true if the current height of the underlying burn blockchain has passed 832,000 blocks.
```

### chain-id <a href="#chain-id" id="chain-id"></a>

Introduced in: Clarity 2

**Output: `uint`**

**Description:**

Returns the 32-bit chain ID of the blockchain running this transaction

**Example:**

```
(print chain-id) ;; Will print 'u1' if the code is running on mainnet, and 'u2147483648' on testnet, and other values on different chains.
```

### contract-caller <a href="#contract-caller" id="contract-caller"></a>

{% hint style="warning" %}
Use caution when leveraging all contract calls, particularly tx-sender and contract-caller as based on the design, you can unintentionally introduce attack surface area. [Read more](https://www.setzeus.com/community-blog-posts/clarity-carefully-tx-sender).
{% endhint %}

Introduced in: Clarity 1

**Output: `principal`**

**Description:**

Returns the caller of the current contract context. If this contract is the first one called by a signed transaction,
the caller will be equal to the signing principal. If `contract-call?` was used to invoke a function from a new contract, `contract-caller`
changes to the _calling_ contract's principal. If `as-contract` is used to change the `tx-sender` context, `contract-caller` _also_ changes
to the same contract principal.

**Example:**

```
(print contract-caller) ;; Will print out a Stacks address of the transaction sender
```

### false <a href="#false" id="false"></a>

Introduced in: Clarity 1

**Output: `bool`**

**Description:**

Boolean false constant.

**Example:**

```
(and true false) ;; Evaluates to false
(or false true)  ;; Evaluates to true
```

### is-in-mainnet <a href="#is-in-mainnet" id="is-in-mainnet"></a>

Introduced in: Clarity 2

**Output: `bool`**

**Description:**

Returns a boolean indicating whether or not the code is running on the mainnet

**Example:**

```
(print is-in-mainnet) ;; Will print 'true' if the code is running on the mainnet
```

### is-in-regtest <a href="#is-in-regtest" id="is-in-regtest"></a>

Introduced in: Clarity 1

**Output: `bool`**

**Description:**

Returns whether or not the code is running in a regression test

**Example:**

```
(print is-in-regtest) ;; Will print 'true' if the code is running in a regression test
```

### none <a href="#none" id="none"></a>

Introduced in: Clarity 1

**Output: `(optional ?)`**

**Description:**

Represents the _none_ option indicating no value for a given optional (analogous to a null value).

**Example:**

```
(define-public (only-if-positive (a int))
  (if (> a 0)
      (some a)
      none))
(only-if-positive 4) ;; Returns (some 4)
(only-if-positive (- 3)) ;; Returns none
```

### stacks-block-height <a href="#stacks-block-height" id="stacks-block-height"></a>

Introduced in: Clarity 3

**Output: `uint`**

**Description:**

Returns the current block height of the Stacks blockchain.

**Example:**

```
(<= stacks-block-height u500000) ;; returns true if the current block-height has not passed 500,000 blocks.
```

### stx-liquid-supply <a href="#stx-liquid-supply" id="stx-liquid-supply"></a>

Introduced in: Clarity 1

**Output: `uint`**

**Description:**

Returns the total number of micro-STX (uSTX) that are liquid in the system as of this block.

**Example:**

```
(print stx-liquid-supply) ;; Will print out the total number of liquid uSTX
```

### tenure-height <a href="#tenure-height" id="tenure-height"></a>

Introduced in: Clarity 3

**Output: `uint`**

**Description:**

Returns the number of tenures that have passed.
At the start of epoch 3.0, `tenure-height` will return the same value as `block-height`, then it will continue to increase as each tenures passes.

**Example:**

```
(< tenure-height u140000) ;; returns true if the current tenure-height has passed 140,000 blocks.
```

### true <a href="#true" id="true"></a>

Introduced in: Clarity 1

**Output: `bool`**

**Description:**

Boolean true constant.

**Example:**

```
(and true false) ;; Evaluates to false
(or false true)  ;; Evaluates to true
```

### tx-sender <a href="#tx-sender" id="tx-sender"></a>

{% hint style="warning" %}
Use caution when leveraging all contract calls, particularly tx-sender and contract-caller as based on the design, you can unintentionally introduce attack surface area. [Read more](https://www.setzeus.com/community-blog-posts/clarity-carefully-tx-sender).
{% endhint %}

Introduced in: Clarity 1

**Output: `principal`**

**Description:**

Returns the original sender of the current transaction, or if `as-contract` was called to modify the sending context, it returns that
contract principal.

**Example:**

```
(print tx-sender) ;; Will print out a Stacks address of the transaction sender
```

### tx-sponsor? <a href="#tx-sponsor?" id="tx-sponsor?"></a>

Introduced in: Clarity 2

**Output: `optional principal`**

**Description:**

Returns the sponsor of the current transaction if there is a sponsor, otherwise returns None.

**Example:**

```
(print tx-sponsor?) ;; Will print out an optional value containing the Stacks address of the transaction sponsor
```

