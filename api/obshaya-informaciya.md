# Общая информация

## Получение API ключа

API ключ для доступа к REST сервису roskassa.net можно сгенерировать на странице настроек магазина [https://my.roskassa.net/shop-settings/](https://my.roskassa.net/shop-settings/)

![](../.gitbook/assets/image%20%289%29.png)

Все данные в запросах к сервису ROSKASSA передаются методом POST по протоколу HTTP на адрес https://api.roskassa.net/\*method\*. Параметры сообщения упаковываются в JSON-объект.

Вместе с запросом необходимо передавать подпись. Подписывать необходимо тело запроса целиком, в том виде, в котором оно отправляется на сервер Банка \(после сериализации тела запроса в JSON для отправки по HTTP\).

{% hint style="info" %}
 В каждом запросе необходимо передавать параметр **nonce**, отличный от предыдущего! Например, можно использовать текущее время в секундах
{% endhint %}

Используйте для подписи ваш секретный ключ. Сформируйте подпись с алгоритмом SHA-256.

```php
<?php

$api_key = 'EEFA1913EA9D9351469B1E5D852A';

$data = array(
    'shop_id' =>'1913EA9D9351469B1E5D852A',
    'nonce' => time(),
);

$body = json_encode($data);
$sign = hash_hmac('sha256', $data, $api_key);


$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.roskassa.net/orders/",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_POSTFIELDS =>$body,
  CURLOPT_HTTPHEADER => array(
    "Authorization: Bearer $sign",
    "Content-Type: application/json"
  ),
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;
```



