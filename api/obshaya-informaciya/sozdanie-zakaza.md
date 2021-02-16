# Создание заказа

{% api-method method="post" host="https://api.roskassa.net/" path="createOrder" %}
{% api-method-summary %}
createOrder
{% endapi-method-summary %}

{% api-method-description %}
Используйте этот метод для получения прямой ссылки на оплату заказа
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
Shop ID
{% endapi-method-parameter %}

{% api-method-parameter name="nonce" type="integer" required=true %}
Уникальный номер запроса
{% endapi-method-parameter %}

{% api-method-parameter name="currency" type="string" required=true %}
Валюта оплаты, RUB/USD/EUR etc
{% endapi-method-parameter %}

{% api-method-parameter name="amount" type="number" required=true %}
Сумма оплаты
{% endapi-method-parameter %}

{% api-method-parameter name="order\_id" type="string" required=true %}
Номер заказа в Вашем магазине
{% endapi-method-parameter %}

{% api-method-parameter name="payment\_system" type="integer" required=true %}
ID платежной системы
{% endapi-method-parameter %}

{% api-method-parameter name="fields" type="array" required=true %}
Данные о покупателе
{% endapi-method-parameter %}

{% api-method-parameter name="receipt" type="array" required=false %}
Данные о корзине
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "type":"success",
    "desc":"",
    "data":{
        "id":755555,
        "url":"https://pay.roskassa.net/complete/755555/7f259f856e7682a6e98179036a623696/"
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

Пример запроса со всеми необходимыми полями

```javascript
{
    "shop_id":"1913EA935149B1E5D852A",
    "nonce":1613435880,
    "currency":"RUB",
    "amount":1200,
    "order_id":"test order",
    "payment_system":5,
    "fields":{
        "email":"user@email.ru",
        "phone":"79111231212"
    },
    "receipt":{
        "items":[
            {
                "name":"test item 1",
                "count":1,
                "price":600
            },
            {
                "name":"test item 2",
                "count":1,
                "price":600
            }
        ]
    }
}
```

