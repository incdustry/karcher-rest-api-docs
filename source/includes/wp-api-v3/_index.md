# Index #

By default, the API provides information about all available endpoints on the site. Authentication is not required to access the API index.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/karcher</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/karcher
```

```javascript
WooCommerce.get("")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php print_r($woocommerce->get('')); ?>
```

```python
print(wcapi.get("").json())
```

```ruby
woocommerce.get("").parsed_response
```

> JSON response example:

```json
{
  "namespace": "wc/karcher",
  "routes": {
    "/wc/karcher": {
      "namespace": "wc/karcher",
      "methods": [
        "GET"
      ],
      "endpoints": [
        {
          "methods": [
            "GET"
          ],
          "args": {
            "namespace": {
              "required": false,
              "default": "wc/karcher"
            },
            "context": {
              "required": false,
              "default": "view"
            }
          }
        }
      ],
      "_links": {
        "self": "https://example.com/wp-json/wc/karcher"
      }
    },
    "/wc/karcher/clients": {
      "namespace": "wc/karcher",
      "methods": [
        "GET"
      ],
      "endpoints": [
        {
          "methods": [
            "GET"
          ],
          "args": {
            "context": {
              "required": false,
              "default": "view",
              "enum": [
                "view",
                "edit"
              ],
              "description": "Scope under which the request is made; determines fields present in response.",
              "type": "string"
            },
            "page": {
              "required": false,
              "default": 1,
              "description": "Current page of the collection.",
              "type": "integer"
            },
            "per_page": {
              "required": false,
              "default": 10,
              "description": "Maximum number of items to be returned in result set.",
              "type": "integer"
            },
            "search": {
              "required": false,
              "description": "Limit results to those matching a string.",
              "type": "string"
            },
            "after": {
              "required": false,
              "description": "Limit response to resources published after a given ISO8601 compliant date.",
              "type": "string"
            },
            "before": {
              "required": false,
              "description": "Limit response to resources published before a given ISO8601 compliant date.",
              "type": "string"
            },
            "exclude": {
              "required": false,
              "default": [],
              "description": "Ensure result set excludes specific IDs.",
              "type": "array",
              "items": {
                "type": "integer"
              }
            },
            "include": {
              "required": false,
              "default": [],
              "description": "Limit result set to specific ids.",
              "type": "array",
              "items": {
                "type": "integer"
              }
            },
            "offset": {
              "required": false,
              "description": "Offset the result set by a specific number of items.",
              "type": "integer"
            },
            "order": {
              "required": false,
              "default": "desc",
              "enum": [
                "asc",
                "desc"
              ],
              "description": "Order sort attribute ascending or descending.",
              "type": "string"
            },
            "orderby": {
              "required": false,
              "default": "date",
              "enum": [
                "date",
                "id",
                "include",
                "title",
                "slug"
              ],
              "description": "Sort collection by object attribute.",
              "type": "string"
            },
            "parent": {
              "required": false,
              "default": [],
              "description": "Limit result set to those of particular parent IDs.",
              "type": "array",
              "items": {
                "type": "integer"
              }
            },
            "parent_exclude": {
              "required": false,
              "default": [],
              "description": "Limit result set to all items except those of a particular parent ID.",
              "type": "array",
              "items": {
                "type": "integer"
              }
            },
            "status": {
              "required": false,
              "default": "any",
              "enum": [
                "any",
                "pending",
                "processing",
                "on-hold",
                "completed",
                "cancelled",
                "refunded",
                "failed"
              ],
              "description": "Limit result set to orders assigned a specific status.",
              "type": "string"
            },
            "customer": {
              "required": false,
              "description": "Limit result set to orders assigned a specific customer.",
              "type": "integer"
            },
            "product": {
              "required": false,
              "description": "Limit result set to orders assigned a specific product.",
              "type": "integer"
            },
            "dp": {
              "required": false,
              "default": 2,
              "description": "Number of decimal points to use in each resource.",
              "type": "integer"
            }
          }
        }
      ],
      "_links": {
        "self": "https://example.com/wp-json/wc/karcher/clients"
      }
    },
    "/wc/karcher/clients/(?P<id>[\\d]+)": {
      "namespace": "wc/karcher",
      "methods": [
        "GET"
      ],
      "endpoints": [
        {
          "methods": [
            "GET"
          ],
          "args": {
            "id": {
              "required": false,
              "description": "Unique identifier for the resource.",
              "type": "integer"
            },
            "context": {
              "required": false,
              "default": "view",
              "enum": [
                "view",
                "edit"
              ],
              "description": "Scope under which the request is made; determines fields present in response.",
              "type": "string"
            }
          }
        }
      ]
    },
    "/wc/karcher/billing": {
      "namespace": "wc/karcher",
      "methods": [
        "GET"
      ],
      "endpoints": [
        {
          "methods": [
            "GET"
          ],
          "args": {
            "context": {
              "required": false,
              "default": "view",
              "enum": [
                "view",
                "edit"
              ],
              "description": "Scope under which the request is made; determines fields present in response.",
              "type": "string"
            },
            "page": {
              "required": false,
              "default": 1,
              "description": "Current page of the collection.",
              "type": "integer"
            },
            "per_page": {
              "required": false,
              "default": 10,
              "description": "Maximum number of items to be returned in result set.",
              "type": "integer"
            },
            "search": {
              "required": false,
              "description": "Limit results to those matching a string.",
              "type": "string"
            },
            "after": {
              "required": false,
              "description": "Limit response to resources published after a given ISO8601 compliant date.",
              "type": "string"
            },
            "before": {
              "required": false,
              "description": "Limit response to resources published before a given ISO8601 compliant date.",
              "type": "string"
            },
            "exclude": {
              "required": false,
              "default": [],
              "description": "Ensure result set excludes specific IDs.",
              "type": "array",
              "items": {
                "type": "integer"
              }
            },
            "include": {
              "required": false,
              "default": [],
              "description": "Limit result set to specific ids.",
              "type": "array",
              "items": {
                "type": "integer"
              }
            },
            "offset": {
              "required": false,
              "description": "Offset the result set by a specific number of items.",
              "type": "integer"
            },
            "order": {
              "required": false,
              "default": "desc",
              "enum": [
                "asc",
                "desc"
              ],
              "description": "Order sort attribute ascending or descending.",
              "type": "string"
            },
            "orderby": {
              "required": false,
              "default": "date",
              "enum": [
                "date",
                "id",
                "include",
                "title",
                "slug"
              ],
              "description": "Sort collection by object attribute.",
              "type": "string"
            },
            "parent": {
              "required": false,
              "default": [],
              "description": "Limit result set to those of particular parent IDs.",
              "type": "array",
              "items": {
                "type": "integer"
              }
            },
            "parent_exclude": {
              "required": false,
              "default": [],
              "description": "Limit result set to all items except those of a particular parent ID.",
              "type": "array",
              "items": {
                "type": "integer"
              }
            },
            "status": {
              "required": false,
              "default": "any",
              "enum": [
                "any",
                "pending",
                "processing",
                "on-hold",
                "completed",
                "cancelled",
                "refunded",
                "failed"
              ],
              "description": "Limit result set to orders assigned a specific status.",
              "type": "string"
            },
            "customer": {
              "required": false,
              "description": "Limit result set to orders assigned a specific customer.",
              "type": "integer"
            },
            "product": {
              "required": false,
              "description": "Limit result set to orders assigned a specific product.",
              "type": "integer"
            },
            "dp": {
              "required": false,
              "default": 2,
              "description": "Number of decimal points to use in each resource.",
              "type": "integer"
            }
          }
        }
      ],
      "_links": {
        "self": "https://example.com/wp-json/wc/karcher/billing"
      }
    },
    "/wc/karcher/billing/(?P<id>[\\d]+)": {
      "namespace": "wc/karcher",
      "methods": [
        "GET"
      ],
      "endpoints": [
        {
          "methods": [
            "GET"
          ],
          "args": {
            "id": {
              "required": false,
              "description": "Unique identifier for the resource.",
              "type": "integer"
            },
            "context": {
              "required": false,
              "default": "view",
              "enum": [
                "view",
                "edit"
              ],
              "description": "Scope under which the request is made; determines fields present in response.",
              "type": "string"
            }
          }
        }
      ]
    },
  },
  "_links": {
    "up": [
      {
        "href": "https://example.com/wp-json/"
      }
    ]
  }
}
```
