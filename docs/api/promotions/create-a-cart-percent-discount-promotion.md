---
id: create-a-percent-discount-promotion
title: Create a Cart Percent Discount Promotion
sidebar_label: Create a Cart Percent Discount Promotion
---

## `POST` Create a Cart Percent Discount Promotion

```http
https://api.moltin.com/v2/promotions/
```

## Parameters

### Headers

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| `Authorization` | Required | `string` | The Bearer token required to get access to the API. |

### Body

 | Name | Required | Type | Description |
 | --- | --- | --- | --- |
 | `type` | Required | `string` | Specifies the type of the resource. The type of resource for promotions is, `promotion`. |
 | `name` | Required | `string` | Specifies a name for the promotion. |
 | `description` | Required | `string` | Specifies a description for the promotion. |
 | `enabled` | Required | `boolean` | Specifies whether the promotion is enabled. The options are `true` or `false`, and the default setting is `false`. |
 | `automatic` | Required  | `boolean` | Specifies whether the promotion is applied automatically to the cart or a code is required to apply the promotion. The default setting is `false`. When this value is set to `true`, a code is autogenerated. If this value is set to `false`, you must create the code manually. For more information about creating codes, see the [Create Promotion Codes](create-promotion-codes.md) section.|
 |`promotion_type`| Required  |`string`| Specifies the type of the promotion. Use `percent_discount` for percentage discount for cart promotions.|
 |`max_discount_value`|Optional|`array`| Specifies an array of currency-value objects, `max_discount_value[].currency` and `max_discount_value[].amount`, that provides the maximum possible discount for the cart. |
 |`min_cart_value`| Optional  |`array`| Specifies an array of currency-value objects, `min_cart_value[].currency` and `min_cart_value[].amount`, that provides the minimum cart value required for the promotion to apply. You can add one or several value specifications in different currencies.|
 |`schema`| Required |`object`| Specifies the promotion value, currency, and the products to be excluded from the promotion, if any. The currency values are provided in a `currencies` array with the values `currencies[].currency` and `currencies[].amount`. The `productID`s or `SKU`s of products to be excluded from the promotion are provided in the `exclude` array. |
 |`start`| Required  |`string`| Specifies the start date and time of the promotion or the start date of the promotion. You can provide a specific time in the HH:MM format. For example, `"start": "2000-01-01 12:00"`. If no time is specified, the default start and end time is set to `00:00`.|
 |`end`| Required  |`string`| Specifies the end date and time of the promotion or the end date of the promotion.|

## Request Example - Curl

 ```bash
 curl -X POST 'https://api.moltin.com/v2/promotions' \
      -H "Authorization: Bearer 68302a5f3742875fbc647a20186a1b8932cad231' \
      -H 'accept: application/json' \
      -H 'content-type: application/json' \
      -H 'x-moltin-auth-store: {{storeID}}' \
    --data-raw '{
   "data": {
     "type": "promotion",
     "name": "10% off",
     "description": "10% off your order!",
     "enabled": true,
     "automatic": false,
     "promotion_type": "percent_discount",
     "max_discount_value": [
       {
         "amount": 1000,
         "currency": "USD"
       }
     ],
     "min_cart_value": [
       {
         "amount": 10000,
         "currency": "USD"
       }
     ],
     "schema": {
       "currencies": [
         {
           "currency": "USD",
           "percentage": 10
         }
       ],
       "exclude": {
         "targets": ["SKU1", "SKU2"]
       }
     },
     "start": "2000-01-01",
     "end": "2100-01-01"
   }
 }`
 ```

### Response

`201 Created`

```json
{
    "data": {
        "type": "promotion",
        "id": "4d87e69b-dcd6-41aa-91a9-a4e9fc9f8218",
        "name": "10% off",
        "description": "10% off your order!",
        "enabled": true,
        "promotion_type": "percent_discount",
        "min_cart_value": [
            {
                "currency": "USD",
                "amount": 10000
            }
        ],
        "max_discount_value": [
            {
                "currency": "USD",
                "amount": 1000
            }
        ],
        "schema": {
            "currencies": [
                {
                    "currency": "USD",
                    "percentage": 10
                }
            ],
            "exclude": {
                "targets": ["SKU1", "SKU2"]
            },
        },
        "start": "2000-01-01T00:00:00Z",
        "end": "2100-01-01T00:00:00Z",
        "meta": {
            "timestamps": {
                "created_at": "2021-06-25T18:02:34.247Z",
                "updated_at": "2021-06-25T18:02:34.247Z"
            }
        }
    }
}
```