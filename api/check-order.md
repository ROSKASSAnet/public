# Проверка заказа

{% api-method method="post" host="https://api.roskassa.net" path="/order/" %}
{% api-method-summary %}
order
{% endapi-method-summary %}

{% api-method-description %}
Получение информации о заказе
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

{% api-method-parameter name="nonce" type="string" required=true %}
Уникальный номер запроса
{% endapi-method-parameter %}

{% api-method-parameter name="order\_id" type="integer" required=false %}
Номер платежа roskassa
{% endapi-method-parameter %}

{% api-method-parameter name="payment\_id" type="string" required=false %}
или номер платежа магазина
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
        "id": 1232,
        "date_created": "2020-11-14 23:32:37",
        "date_payed": "2020-11-14 23:33:39",
        "status": 1,
        "payment_system_id": 10,
        "currency_id": 1,
        "amount": "64.18000000",
        "fee": "4.00000000",
        "email": "user@site.ru",
        "test_order": 0,
        "payment_id": "Order #17854"
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



