# Get user transfers
> `POST https://domain.com/user/transfers`

Get user transfers

### HTTP Request
`POST /user/transfers`

```
Response example
```

```json
{
    "id": null,
    "jsonrpc": "2.0",
    "result": {
        "items": [
            {
                "age": "22 hours ago",
                "amount_in": 0.001,
                "amount_out": 0.001,
                "amount_out_base": 0,
                "confirmations": 0,
                "create_date": "2017-03-14 12:12:01",
                "currency_base": "EUR",
                "currency_in": "BTC",
                "currency_out": "BTC",
                "description": "test",
                "direction": "from",
                "operation_id": "d2e2300c32865fb01f9cb9b3281de0fa57e5e8ff4317594757add54ea2637da5",
                "recipient": {
                    "country_code": "_blank",
                    "email": false,
                    "name": "1PZVmyMPc42ZF6FpWejNuKNDpB6vufKG6T"
                },
                "refuse_reason": false,
                "seen": true,
                "sender": {
                    "country_code": "es",
                    "email": "in+140317@ammalgamma.ru",
                    "id": 5992,
                    "name": "Igor"
                },
                "stage": {
                    "name": "Complete",
                    "num": 3
                }
            },
            {
                "age": "22 hours ago",
                "amount_in": 0.0001,
                "amount_out": 0.0001,
                "amount_out_base": 0,
                "confirmations": 0,
                "create_date": "2017-03-14 11:30:19",
                "currency_base": "EUR",
                "currency_in": "BTC",
                "currency_out": "BTC",
                "description": "test",
                "direction": "from",
                "operation_id": "ce735c8122f13b5091eef9b6f0837a8e920874ec4d0c8583f59ca143d0e53431",
                "recipient": {
                    "country_code": "_blank",
                    "email": false,
                    "name": "1PZVmyMPc42ZF6FpWejNuKNDpB6vufKG6T"
                },
                "refuse_reason": false,
                "seen": true,
                "sender": {
                    "country_code": "es",
                    "email": "in+140317@ammalgamma.ru",
                    "id": 5992,
                    "name": "Igor"
                },
                "stage": {
                    "name": "Complete",
                    "num": 3
                }
            }
        ],
        "total": {
            "currency": "EUR",
            "from": 0,
            "to": 0
        }
    }
}
```
