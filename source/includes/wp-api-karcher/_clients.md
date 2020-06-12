# Clients #

The clients API allows you to view a batch of clients.

## Client properties ##

| Attribute              | Type      | Description |
|------------------------|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `id`                  | integer   | Unique identifier for the resource. <i class="label label-info">read-only</i>                                                                                                         |
| `fullname`            | string    | Fullname. <i class="label label-info">read-only</i>                                                                                                         |
| `type`                | string    | Type with which the client was created. Options: `PN` and `PJ`.                                                                                                      |
| `document_type`       | string    | Document type with which the client was created. Options: `C` and `N`.                                                                                                       |
| `cc`                  | string    | This field is shown when the client was registered with CC. <i class="label label-info">read-only</i>                                                                                                         |
| `nit`                 | string    | This field is shown when the client was registered with NIT. <i class="label label-info">read-only</i>                                                                                                         |
| `document_number`     | string    | Document number. <i class="label label-info">read-only</i>                                                                                                         |
| `address_1`           | string    | Client address. <i class="label label-info">read-only</i>                                                                                                         |
| `address_2`           | string    | Additional information from the client's address. It can be empty. <i class="label label-info">read-only</i>                                                                                                         |
| `address_1`           | string    | Client address. <i class="label label-info">read-only</i>                                                                                                         |
| `country`             | string    | Country code in ISO 3166-1 alpha-2 format. <i class="label label-info">read-only</i>                                                                                  |
| `state`               | string    | ISO code or name of the state, province or district. <i class="label label-info">read-only</i>                                                                                  |
| `state_code`          | string    | Code of the state - DIAN (only for clients registered as Colombians). It can be empty. <i class="label label-info">read-only</i>                                                                                                         |
| `city`                | string | City name. <i class="label label-info">read-only</i>                                                                                                         |
| `transport_zone`      | string | Transport zone. <i class="label label-info">read-only</i>                                                                                                         |
| `class_tax`           | string | Class tax. <i class="label label-info">read-only</i>                                                                                                         |
| `branch_code`         | string | Branch code. <i class="label label-info">read-only</i>                                                                                                         |
| `sales_chanel`        | string | Sales chanel. <i class="label label-info">read-only</i>                                                                                                         |
| `responsable`         | string | Responsable. <i class="label label-info">read-only</i>                                                                                                         |
| `seller`              | string | Seller. <i class="label label-info">read-only</i>                                                                                                         |
| `currency`             | string    | Currency the order was created with, in ISO format. Options: `AED`, `AFN`, `ALL`, `AMD`, `ANG`, `AOA`, `ARS`, `AUD`, `AWG`, `AZN`, `BAM`, `BBD`, `BDT`, `BGN`, `BHD`, `BIF`, `BMD`, `BND`, `BOB`, `BRL`, `BSD`, `BTC`, `BTN`, `BWP`, `BYR`, `BZD`, `CAD`, `CDF`, `CHF`, `CLP`, `CNY`, `COP`, `CRC`, `CUC`, `CUP`, `CVE`, `CZK`, `DJF`, `DKK`, `DOP`, `DZD`, `EGP`, `ERN`, `ETB`, `EUR`, `FJD`, `FKP`, `GBP`, `GEL`, `GGP`, `GHS`, `GIP`, `GMD`, `GNF`, `GTQ`, `GYD`, `HKD`, `HNL`, `HRK`, `HTG`, `HUF`, `IDR`, `ILS`, `IMP`, `INR`, `IQD`, `IRR`, `IRT`, `ISK`, `JEP`, `JMD`, `JOD`, `JPY`, `KES`, `KGS`, `KHR`, `KMF`, `KPW`, `KRW`, `KWD`, `KYD`, `KZT`, `LAK`, `LBP`, `LKR`, `LRD`, `LSL`, `LYD`, `MAD`, `MDL`, `MGA`, `MKD`, `MMK`, `MNT`, `MOP`, `MRO`, `MUR`, `MVR`, `MWK`, `MXN`, `MYR`, `MZN`, `NAD`, `NGN`, `NIO`, `NOK`, `NPR`, `NZD`, `OMR`, `PAB`, `PEN`, `PGK`, `PHP`, `PKR`, `PLN`, `PRB`, `PYG`, `QAR`, `RON`, `RSD`, `RUB`, `RWF`, `SAR`, `SBD`, `SCR`, `SDG`, `SEK`, `SGD`, `SHP`, `SLL`, `SOS`, `SRD`, `SSP`, `STD`, `SYP`, `SZL`, `THB`, `TJS`, `TMT`, `TND`, `TOP`, `TRY`, `TTD`, `TWD`, `TZS`, `UAH`, `UGX`, `USD`, `UYU`, `UZS`, `VEF`, `VND`, `VUV`, `WST`, `XAF`, `XCD`, `XOF`, `XPF`, `YER`, `ZAR` and `ZMW`. Default is `USD`. |


## Retrieve an client ##

This API lets you retrieve and view a specific client.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/karcher/clients/&lt;id&gt;</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/karcher/clients/715 \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("clients/715")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php print_r($woocommerce->get('clients/715')); ?>
```

```python
print(wcapi.get("clients/715").json())
```

```ruby
woocommerce.get("clients/715").parsed_response
```

> JSON response example:

```json
{
  "id": 715,
  "fullname": "Omar Fandiño",
  "type": "PN",
  "document_type": "C",
  "cc": "92001006",
  "document_number": "92001006",
  "address_1": "Calle 2 # 99 - 120",
  "address_2": "",
  "country": "CO",
  "state": "VAC",
  "state_code": "76",
  "city": "Cali",
  "transport_zone": "0000000001",
  "class_tax": "PN",
  "branch_code": "900000",
  "sales_chanel": "953000",
  "responsable": "7083000072",
  "seller": "7083000072",
  "currency": "COP"
}
```

#### Available parameters ####

| Parameter | Type   | Description                                       |
|-----------|--------|---------------------------------------------------|
| `dp`      | string | Number of decimal points to use in each resource. |


## List all clients ##

This API helps you to view all the clients.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/karcher/clients</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/karcher/clients \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("clients")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php print_r($woocommerce->get('clients')); ?>
```

```python
print(wcapi.get("clients").json())
```

```ruby
woocommerce.get("clients").parsed_response
```

> JSON response example:

```json
[
  {
    "id": 727,
    "fullname": "John Doe",
    "type": "PN",
    "document_type": "C",
    "cc": "1144154123",
    "document_number": "1144154123",
    "address_1": "Calle 5 # 10 - 20",
    "address_2": "",
    "country": "CO",
    "state": "CUN",
    "state_code": "11",
    "city": "Bogotá D.C",
    "transport_zone": "0000000001",
    "class_tax": "PN",
    "branch_code": "900000",
    "sales_chanel": "953000",
    "responsable": "7083000072",
    "seller": "7083000072",
    "currency": "COP"
  },
  {
    "id": 715,
    "fullname": "Omar Fandiño",
    "type": "PN",
    "document_type": "C",
    "cc": "92001006",
    "document_number": "92001006",
    "address_1": "Calle 2 # 99 - 120",
    "address_2": "",
    "country": "CO",
    "state": "VAC",
    "state_code": "76",
    "city": "Cali",
    "transport_zone": "0000000001",
    "class_tax": "PN",
    "branch_code": "900000",
    "sales_chanel": "953000",
    "responsable": "7083000072",
    "seller": "7083000072",
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