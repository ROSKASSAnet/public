# Баланс

{% api-method method="post" host="https://api.roskassa.net" path="/balance/" %}
{% api-method-summary %}
balance
{% endapi-method-summary %}

{% api-method-description %}
Получение баланса всех кошельков
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Подпись запроса
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="shop\_id" type="string" required=true %}
Public key магазина
{% endapi-method-parameter %}

{% api-method-parameter name="nonce" type="integer" required=true %}
Уникальный номер запроса
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "type": "success",
    "desc": "",
    "data": {
        "user_id": 1,
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



