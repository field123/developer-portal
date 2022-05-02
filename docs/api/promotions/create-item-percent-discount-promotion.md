---
id: create-item-percent-discount-promotion
title: Create Percent Discount Promotion for Items
sidebar_label: Create Item Percent Discount Promotions
---

## `POST` Create Item Percent Discount Promotions

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

## Body

 | Name | Required | Type | Description |
 | --- | --- | --- | --- |
 | `type` | Required | `string` | Specifies the type of the resource. The type of resource for promotions is, `promotion`. |
 | `name` | Required | `string` | Specifies a name for the promotion. |
 | `description` | Required | `string` | Specifies a description for the promotion. |
 | `enabled` | Required | `boolean` | Specifies whether the promotion is enabled. The options are `true` or `false`, and the default setting is `false`. |
 | `automatic` | Required  | `boolean` | Specifies whether the promotion is applied automatically to the cart or a code is required to apply the promotion. The default setting is `false`. When this value is set to `true`, a code is autogenerated. If this value is set to `false`, you must create the code manually. For more information about creating codes, see the [Create Promotion Codes](create-promotion-codes.md) section.|
 |`promotion_type`| Required  |`string`| Specifies the type of the promotion. Use `item_percent_discount` for the percentage discount for item promotions.|
 |`min_cart_value`| Optional  |`array`| Specifies an array of currency-value objects, `min_cart_value[].currency` and `min_cart_value[].amount`, that provides the minimum cart value required for the promotion to apply. You can add one or several value specifications in different currencies.|
 |`max_applications_per_cart`| Optional | `integer`| Specifies the maximum number of application of a promotion per cart.|
 |`max_discount_value`|Optional|`array`| Specifies an array of currency-value objects, `max_discount_value[].currency` and `max_discount_value[].amount`, that provides the maximum possible discount for the item. |
 |`schema`| Required |`object`| Specifies the list of products to include in the promotion and the discount percentage. For example, `targets:["sku1", "sku2"], "percent": 50`. Set `"targets": "all"` if you want to apply the promotion to all SKUs. Leaving this field empty might cause errors. |
 |`start`| Required  |`string`| Specifies the start date and time of the promotion or the start date of the promotion. You can provide a specific time in the HH:MM format. For example, `"start": "2000-01-01 12:00"`. If no time is specified, the default start and end time is set to `00:00`.|
 |`end`| Required  |`string`| Specifies the end date and time of the promotion or the end date of the promotion.|

## Request Example - Curl

```bash
curl -X POST 'https://api.moltin.com/v2/promotions' \
     -H "Authorization: Bearer d3233921c41fe6f027dbb09e45f4d11dba015a18' \
     -H 'accept: application/json' \
     -H 'content-type: application/json' \
     -H 'x-moltin-auth-store: {{storeID}}' \
     --data-raw '{
  "data": {
    "type": "promotion",
    "name": "Item percent discount promotion example",
    "description": "50% off for SKU1",
    "enabled": true,
    "automatic": false,
    "promotion_type": "item_percent_discount",
    "schema": {
      "targets": ["sku1","sku2"],
      "percent": 50
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
      "id": "95dc7454-affb-4aa1-ae5c-364a5f7cf336",
      "name": "Item percent discount promotion example",
      "description": "50% off for SKU1",
      "enabled": true,
      "promotion_type": "item_percent_discount",
      "schema": {
        "targets": ["sku1","sku2"],
          "percent": 50
      },
      "start": "2000-01-01T00:00:00Z",
      "end": "2100-01-01T00:00:00Z",
      "meta": {
          "timestamps": {
              "created_at": "2021-06-30T21:43:11.661Z",
              "updated_at": "2021-06-30T21:43:11.661Z"
          }
      }
  }
}
```