---
id: create-fixed-bundle-discount-promotion
title: Create Fixed Bundle Discount Promotions
sidebar_label: Create Fixed Bundle Discount Promotions
---

## `POST` Create Fixed Bundle Discount Promotions

```http
https://api.moltin.com/v2/promotions/
```

:::note
Line-item discounts are only supported by the line calculation method. For more information about this method, see the [Calculation Method](../advanced/settings/index.md#calculation-method) section.
:::

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
 |`promotion_type`| Required  |`string`| Specifies the type of the promotion. Use `bundle_fixed_discount` for bundle promotions.|
 |`max_applications_per_cart`| Optional | `integer`| Specifies the maximum number of application of the promotion per cart.|
 |`min_cart_value`| Optional  |`array`| Specifies an array of currency-value objects, `min_cart_value[].currency` and `min_cart_value[].amount`, that provide the minimum cart value required for the promotion to apply. You can add one or several value specifications in different currencies.|
 |`schema`| Required |`object`| Specifies the bundle requirements and currencies. In bundle requirements, specify the product SKUs and required quantity of products to apply bundle promotion. |
 |`start`| Required  |`string`| Specifies the start date and time of the promotion or the start date of the promotion. You can provide a specific time in the HH:MM format. For example, `"start": "2000-01-01 12:00"`. If no time is specified, the default start and end time is set to `00:00`.|
 |`end`| Required  |`string`| Specifies the end date and time of the promotion or the end date of the promotion.|

## Request Example - Curl

 ```bash
 curl -X POST 'https://api.moltin.com/v2/promotions' \
      -H "Authorization: Bearer 96d8bcaca17a2db01b44b16de520a4765acad1b4' \
      -H 'accept: application/json' \
      -H 'content-type: application/json' \
      -H 'x-moltin-auth-store: {{storeID}}' \
      --data-raw '{
     "data": {
       "type": "promotion",
       "name": "Fixed bundle promotion example",
       "description": "SKU1 and SKU2 for $150",
       "enabled": true,
       "automatic": true,
       "promotion_type": "bundle_fixed_discount",
       "max_applications_per_cart":1,
       "schema": {
         "requirements": [
           {
             "targets": [
               "SKU1"
             ],
             "quantity": 1
           },
           {
             "targets": [
               "SKU2"
             ],
             "quantity": 1
           }
         ],
         "currencies": [
           {
             "amount": 15000,
             "currency": "USD"
           }
         ]
       },
       "start": "2000-01-01",
       "end": "2100-01-01"
     }
   }'
 ```

### Response

`201 Created`

```json
{
    "data": {
        "type": "promotion",
        "id": "cb7f218f-bb02-43f3-a05b-88cad8e34339",
        "name": "Fixed bundle promotion example",
        "description": "SKU1 and SKU2 for $150",
        "enabled": true,
        "automatic": true,
        "promotion_type": "bundle_fixed_discount",
        "max_applications_per_cart":1,
        "schema": {
            "requirements": [
                {
                    "targets": [
                        "SKU1"
                    ],
                    "quantity": 1
                },
                {
                    "targets": [
                        "SKU2"
                    ],
                    "quantity": 1
                }
            ],
            "currencies": [
                {
                    "currency": "USD",
                    "amount": 15000
                }
            ]
        },
        "start": "2000-01-01T00:00:00Z",
        "end": "2100-01-01T00:00:00Z",
        "meta": {
            "timestamps": {
                "created_at": "2021-06-30T17:30:01.662Z",
                "updated_at": "2021-06-30T17:30:01.662Z"
            }
        }
    }
}
```
