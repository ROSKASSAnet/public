# Проверка выплаты

{% api-method method="post" host="https://api.roskassa.net" path="/withdrawal/" %}
{% api-method-summary %}
withdrawal
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
{% api-method-parameter name="shop\_id" type="string" required=true %}
Public key магазина
{% endapi-method-parameter %}

{% api-method-parameter name="nonce" type="integer" required=true %}
Уникальный номер запроса
{% endapi-method-parameter %}

{% api-method-parameter name="order\_id" type="string" required=false %}
Номер выплаты в Roskassa
{% endapi-method-parameter %}

{% api-method-parameter name="payment\_id" type="string" required=false %}
или номер выплаты магазина
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
        "currency_id": 1,
        "amount": "64.18000000"
        "payment_id": "Order #17854"
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



