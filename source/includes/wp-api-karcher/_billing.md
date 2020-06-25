# Billing #

The billing API allows you to view a batch of invoices.

## Billing properties ##

| Attribute              | Type      | Description |
|------------------------|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `id`                  | integer   | Unique identifier for the resource. <i class="label label-info">read-only</i>                                                                                                         |
| `order`               | string    | Order code generated for Karcher. <i class="label label-info">read-only</i>                                                                                                         |
| `shipping_total`      | string    | Total shipping amount for the  order. <i class="label label-info">read-only</i>                                                                                                          |
| `shipping_tax`        | string    | Total shipping tax amount for the order. <i class="label label-info">read-only</i>                                                                                                          |
| `cart_tax`            | string    | Sum of line item taxes only. <i class="label label-info">read-only</i>                                                                                                         |
| `total`               | string    | Grand total. <i class="label label-info">read-only</i>                                                                                                         |
| `total_tax`           | string    | Sum of all taxes. <i class="label label-info">read-only</i>                                                                                                         |
| `line_items`          | array     | List of order line items. See [Line Items Properties](#line-items-properties)                                                                                     |
| `currency`             | string    | Currency the order was created with, in ISO format. Options: `AED`, `AFN`, `ALL`, `AMD`, `ANG`, `AOA`, `ARS`, `AUD`, `AWG`, `AZN`, `BAM`, `BBD`, `BDT`, `BGN`, `BHD`, `BIF`, `BMD`, `BND`, `BOB`, `BRL`, `BSD`, `BTC`, `BTN`, `BWP`, `BYR`, `BZD`, `CAD`, `CDF`, `CHF`, `CLP`, `CNY`, `COP`, `CRC`, `CUC`, `CUP`, `CVE`, `CZK`, `DJF`, `DKK`, `DOP`, `DZD`, `EGP`, `ERN`, `ETB`, `EUR`, `FJD`, `FKP`, `GBP`, `GEL`, `GGP`, `GHS`, `GIP`, `GMD`, `GNF`, `GTQ`, `GYD`, `HKD`, `HNL`, `HRK`, `HTG`, `HUF`, `IDR`, `ILS`, `IMP`, `INR`, `IQD`, `IRR`, `IRT`, `ISK`, `JEP`, `JMD`, `JOD`, `JPY`, `KES`, `KGS`, `KHR`, `KMF`, `KPW`, `KRW`, `KWD`, `KYD`, `KZT`, `LAK`, `LBP`, `LKR`, `LRD`, `LSL`, `LYD`, `MAD`, `MDL`, `MGA`, `MKD`, `MMK`, `MNT`, `MOP`, `MRO`, `MUR`, `MVR`, `MWK`, `MXN`, `MYR`, `MZN`, `NAD`, `NGN`, `NIO`, `NOK`, `NPR`, `NZD`, `OMR`, `PAB`, `PEN`, `PGK`, `PHP`, `PKR`, `PLN`, `PRB`, `PYG`, `QAR`, `RON`, `RSD`, `RUB`, `RWF`, `SAR`, `SBD`, `SCR`, `SDG`, `SEK`, `SGD`, `SHP`, `SLL`, `SOS`, `SRD`, `SSP`, `STD`, `SYP`, `SZL`, `THB`, `TJS`, `TMT`, `TND`, `TOP`, `TRY`, `TTD`, `TWD`, `TZS`, `UAH`, `UGX`, `USD`, `UYU`, `UZS`, `VEF`, `VND`, `VUV`, `WST`, `XAF`, `XCD`, `XOF`, `XPF`, `YER`, `ZAR` and `ZMW`. Default is `USD`. |

### Line Items Properties ###

|   Attribute    |  Type    |   Description   |
|----------------|---------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `sku`          | string  | Product SKU <i class="label label-info">read-only</i>  |
| `quantity`     | integer | Quantity <i class="label label-info">read-only</i> |
| `subtotal`     | string  | Line item subtotal <i class="label label-info">read-only</i> |
| `subtotal_tax` | string  | Line item tax subtotal <i class="label label-info">read-only</i> |
| `total`        | string  | Line item total <i class="label label-info">read-only</i>  |
| `total_tax`    | string  | Line item tax total <i class="label label-info">read-only</i>  |

## Retrieve an billing ##

This API lets you retrieve and view a specific invoice.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/karcher/billing/&lt;id&gt;</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/karcher/billing/4969 \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("billing/4969")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php print_r($woocommerce->get('billing/4969')); ?>
```

```python
print(wcapi.get("billing/4969").json())
```

```ruby
woocommerce.get("billing/4969").parsed_response
```

> JSON response example:

```json
{
  "id": 4969,
  "order": "KAR/26432764/OC-4969",
  "shipping_total": "6040",
  "shipping_tax": "0",
  "cart_tax": "0",
  "total": "195840",
  "total_tax": "0",
  "line_items": [
    {
      "sku": "9.810-007.0",
      "quantity": 1,
      "subtotal": "129900",
      "subtotal_tax": "0",
      "total": "129900",
      "total_tax": "0"
    },
    {
      "sku": "6.295-771.0",
      "quantity": 1,
      "subtotal": "59900",
      "subtotal_tax": "0",
      "total": "59900",
      "total_tax": "0"
    }
  ],
  "currency": "COP"
}
```

#### Available parameters ####

| Parameter | Type   | Description                                       |
|-----------|--------|---------------------------------------------------|
| `dp`      | string | Number of decimal points to use in each resource. |


## List all billing ##

This API helps you to view all the invoices.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/karcher/billing</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/karcher/billing \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("billing")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php print_r($woocommerce->get('billing')); ?>
```

```python
print(wcapi.get("billing").json())
```

```ruby
woocommerce.get("billing").parsed_response
```

> JSON response example:

```json
[
  {
    "id": 4969,
    "order": "KAR/26432764/OC-4969",
    "shipping_total": "6040",
    "shipping_tax": "0",
    "cart_tax": "0",
    "total": "195840",
    "total_tax": "0",
    "line_items": [
      {
        "sku": "9.810-007.0",
        "quantity": 1,
        "subtotal": "129900",
        "subtotal_tax": "0",
        "total": "129900",
        "total_tax": "0"
      },
      {
        "sku": "6.295-771.0",
        "quantity": 1,
        "subtotal": "59900",
        "subtotal_tax": "0",
        "total": "59900",
        "total_tax": "0"
      }
    ],
    "currency": "COP"
  }
  {
    "id": 4968,
    "order": "KAR/26469764/OC-4968",
    "shipping_total": "0",
    "shipping_tax": "0",
    "cart_tax": "0",
    "total": "279900",
    "total_tax": "0",
    "line_items": [
      {
        "sku": "1.633-038.0",
        "quantity": 1,
        "subtotal": "279900",
        "subtotal_tax": "0",
        "total": "279900",
        "total_tax": "0"
      }
    ],
    "currency": "COP"
  }
]
```

#### Available parameters ####

| Parameter        | Type    | Description                                                                                                                                                                              |
|------------------|---------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `seen`           | boolean | Show again the items that have already been seen by Karcher. Default is `false`.                                                                                                                                          |
| `page`           | integer | Current page of the collection. Default is `1`.                                                                                                                                          |
| `per_page`       | integer | Maximum number of items to be returned in result set. Default is `10`.                                                                                                                   |
| `search`         | string  | Limit results to those matching a string.                                                                                                                                                |
| `after`          | string  | Limit response to resources published after a given ISO8601 compliant date. ISO8601 format: `YYYY-MM-DDTHH:MM:SS`                                                                                                              |
| `before`         | string  | Limit response to resources published before a given ISO8601 compliant date. ISO8601 format: `YYYY-MM-DDTHH:MM:SS`                                                                                                             |
| `exclude`        | array   | Ensure result set excludes specific IDs.                                                                                                                                                 |
| `include`        | array   | Limit result set to specific ids.                                                                                                                                                        |
| `offset`         | integer | Offset the result set by a specific number of items.                                                                                                                                     |
| `orderby`        | string  | Sort collection by object attribute. Options: `date`, `id`, `include`, `title` and `slug`. Default is `date`.                                                                            |
| `dp`             | integer | Number of decimal points to use in each resource. Default is `2`.                                                                                                                        |