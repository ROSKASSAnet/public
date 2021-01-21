# Вывод средств

{% api-method method="post" host="https://api.roskassa.net" path="/createWithdrawal/" %}
{% api-method-summary %}
createWithdrawal
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Подпись запроса
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="payment\_system" type="integer" required=true %}
Платежная система
{% endapi-method-parameter %}

{% api-method-parameter name="shop\_id" type="string" required=true %}
Public key магазина
{% endapi-method-parameter %}

{% api-method-parameter name="nonce" type="integer" required=true %}
Уникальный номер запроса
{% endapi-method-parameter %}

{% api-method-parameter name="currency" type="string" required=true %}
Валюта RUB/USD/EUR etc
{% endapi-method-parameter %}

{% api-method-parameter name="account" type="string" required=true %}
Номер счета для вывода
{% endapi-method-parameter %}

{% api-method-parameter name="amount" type="number" required=true %}
Сумма
{% endapi-method-parameter %}

{% api-method-parameter name="payment\_id" type="integer" required=false %}
Идентификатор вывода
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```javascript
{
    "type": "success",
    "desc": "",
    "data": {
        "order_id": 7911,
        "balance": {
            "RUB": "1396.68",
            "USD": "0.00",
            "EUR": "1.23",
            "UAH": "0.00"
        }
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



