# Список магазинов

{% api-method method="post" host="https://api.roskassa.net" path="/shops/" %}
{% api-method-summary %}
Shops
{% endapi-method-summary %}

{% api-method-description %}
Получение списка ваших магазинов
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
        "shops": [
            {
                "id": 1,
                "date_added": "2020-11-03 18:04:07",
                "name": "DEMO1",
                "url": "https://demo1",
                "status": 1,
                "public_key": "D0F98E7DD86BB7500914",
                "desc": "DEMO1 SHOP"
            },
            {
                "id": 2,
                "date_added": "2020-11-03 22:38:58",
                "name": "DEMO2",
                "url": "https://demo2",
                "status": 0,
                "public_key": "1913EA935149B1E5D852A",
                "desc": "DEMO2 SHOP"
            }
        ]
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



