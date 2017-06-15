# Get user wallets
> `POST https://domain.com/user/get_wallets_list/1.0/json`

Get user wallets

### HTTP Request
`POST /user/get_wallets_list/1.0/json`

```
Response example
```


```json
{
  "id": null,
    "jsonrpc": "2.0",
    "result": [
    {
      "ac_currency_id": [181, "BTC"],
      "acc_number": "1BhrT6d3BLrS2kfT2BQMpJiiUHj8WyCbSw",
      "balance": 1.08274,
      "code": "1BhrT6d3BLrS2kfT2BQMpJiiUHj8WyCbSw",
      "create_date": "2016-06-10 10:28:50",
      "currency_id": [181, "BTC"],
      "display_name": "1BhrT6d3BLrS2kfT2BQMpJiiUHj8WyCbSw",
      "id": 338,
      "name": "/"
    },
    {
      "ac_currency_id": [1, "EUR"],
      "acc_number": "13412341324",
      "balance": 22,
      "code": "13412341324",
      "create_date": "2017-02-28 16:35:15",
      "currency_id": [1, "EUR"],
      "display_name": "13412341324",
      "id": 4067,
      "name": "/"
    }
  ]
}
```

# Get wallet operations
> `POST https://domain.com/user/accounts/<account_id>/operations/`

```
Response example
```

```json
{
    "id": null,
    "jsonrpc": "2.0",
    "result": {
        "balance": "4.13",
        "currency_name": "BTC",
        "items": [
            {
                "amount": 0.11,
                "balance": 4.13,
                "date": "2017-03-09",
                "name": "Sell bitcoin",
                "num": "EUR/2017/03/17",
                "operation_ref": "ff525a15",
                "recipient": {
                    "name": "Money-4",
                    "surname": "Limited",
                    "id": 5067
                },
                "reference": "Sell bitcoin"
            }
        ],
        "topup": "0.11",
        "withdraw": "0.0"
    }
}
```

Get partner operations for specified acccount and date range.
If no date_from and date_to specified returns operations within last 30 days.

### HTTP Request
`POST /user/accounts/<account_id>/operations/`

### Arguments

Parameter | Type | Required | Description
--------- | ----------- | ----------- | -----------
date_from | string | Optional | Datetime moment including timezone, ex: 2016-03-11T10:14:00.190Z
date_to | string | Optional | Datetime moment including timezone, ex: 2016-03-11T10:14:00.190Z

<aside class="notice">
For fetching data for wallets containing slash symbols '/' please substitute slash for undescrore symbol '_'. Ex., 'W/1234' should be requested as 'W_1234'
</aside>

# Get user cards
> `POST https://domain.com/user/get_cards/1.0/json`

Get user saved cards

### HTTP Request
`POST /user/get_cards/1.0/json`

```
Response example
```


```json
{
    "id": null,
    "jsonrpc": "2.0",
    "result": [
        {
            "code": 4,
            "expiration_date": "2019-10-31 23:59:59",
            "pan_number": "42424242",
            "payment_system": "Visa"
        }
    ]
}
```

# Get deposit methods

> `POST http://domain.com/user/get_deposit_methods`

```
Successful response
```

```json
{
    "id": null,
    "jsonrpc": "2.0",
    "result":
    {
        "status": "success",
        "deposit_methods":
        [
            {
                "id": 15,
                "partner_id": 13,
                "deposit_method": "Swedbank NOK Normal",
                "bank_name": "Swedbank",
                "bank_country": "Finland",
                "bank_street": "Ilveskatu 5",
                "bank_city": "Helsinki",
                "bic": "SWED",
                "currency": "NOK",
                "currency_symbol": "kr",
                "int_bank_account": "FI33 0017 2247 0173 58",
                "int_bank_swift": "SWED",
                "int_bank": "Swedbank",
                "account_number": "FI33 0017 2247 0173 58",
                "account_owner": "Baltic Soft",
                "bank_code": "001",
                "bank_zip": false,
                "external_notes": "Swedbank External Notes",
                "help": "Swedbank Help",
                "reference": "nordea.no",
                "minimum": 50
            }
        ]
    }
}
```

```
Unsuccessful response
```

```json
{
    "jsonrpc": "2.0", 
    "id": null, 
    "result": 
    {
        "status": "error",
        "message": "Managing company is not found"
    }
}
```

### HTTP Request

`POST http://domain.com/user/get_deposit_methods`

### Arguments

Parameter | Type | Required | Description
--------- | ----------- | ----------- | -----------
currency | string | Optional | Currency name

### Returns
Dictionary with list with data about available deposit methods.

Contains fields:

Parameter | Description | Possible values 
--------- | ----------- | -----------
id | method id | *
partner_id | current partner id | *
deposit_method | method name | *
bank_name | bank name | *
bank_country | bank address: country | *
bank_street | bank address: street | *
bank_city | bank address: city | *
bank_zip | bank address: post index | *
bic | bank identification code | *
bank_code | bank code | *
int_bank_account | intermediary bank account number | *
int_bank_swift | intermediary bank SWIFT code | *
int_bank | intermediary bank name | *
currency | currency name | *
currency_symbol | currency symbol | *
account_number | account number | *
account_owner | account owner | *
external_notes | bank external notes | *
help | bank help information | *
reference | account reference | *
minimum | minimum sum in current currency | *

