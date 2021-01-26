---
description: >-
  С Roskassa и продавец, и покупатель получают «электронного кассира», который
  значительно упрощает проведение операций и ускоряет платежи.
---

# Создание платежа

Для создания платежа нужно передать необходимые параметры на специальный урл https://pay.roskassa.net/?params

Обязательные параметры

| Ключ | Описание |
| :--- | :--- |
| shop\_id | Публичный ключ проекта |
| amount | Сумма платежа |
| order\_id | Идентификатор заказа \(номер платежа или email клиента\) |
| currency | Валюта платежа \(RUB, USD, EUR\) |
| sign | Подпись запроса |

Дополнительные параметры

| Ключ | Описание |
| :--- | :--- |
| lang | Язык интерфейса \(ru, en\) |
| test | Если указан со значением "1" - оплата пройдет в тестовом режиме |
| payment\_system | [ID платежной системы](../../spravochnaya-informaciya/payment-systems/)  |

Для формирования подписи необходимо отсортировать по ключу все обязательные параметры,  объединить пары ключ/значение символом **&** и добавить в конец  Ваш секретный ключ. Затем захешировать получившуюся строку  MD5, например

```php
<?php 
$secret = 'GB%^&*YJni677';
$data = array(
    'shop_id'=>'D0F98E7D7742609DC508D86BB7500914',
    'amount'=>100,
    'currency'=>'RUB',
    'order_id'=>'123',
);
ksort($data);
$str = http_build_query($data);
$sign = md5($str . $secret);

```

**Внимание!** Если в форму оплаты был передан флаг тестовой оплаты **test=1** , этот параметр так же участвует в формировании подписи:

```php
<?php 
$secret = 'GB%^&*YJni677';
$data = array(
    'shop_id'=>'D0F98E7D7742609DC508D86BB7500914',
    'amount'=>100,
    'currency'=>'RUB',
    'order_id'=>'123',
    'test'=>1,
);
ksort($data);
$str = http_build_query($data);
$sign = md5($str . $secret);

```

Возможен переход сразу в платежную систему, если Вы готовы передать все данные для оплаты во входящем запросе. Для этого отправить данные нужно методом POST на урл https://pay.roskassa.net/form/ обязательно указать параметр payment\_system и передать все обязательные поля для этого способа оплаты. В большинстве случаев это **email**, для дополнительной информации обратитесь в службу поддержки.

Пример:

```php
<form action="https://pay.roskassa.net/form/" method="post">
<input type="hidden" name="shop_id" value="D0F98E7D7742609DC508D86BB7500914">
<input type="hidden" name="amount" value="100">
<input type="hidden" name="order_id" value="123">
<input type="hidden" name="lang" value="ru">
<input type="hidden" name="currency" value="RUB">
<input type="hidden" name="payment_system" value="11">
<input type="hidden" name="fields[email]" value="user@site.ru">
<input type="hidden" name="sign" value="e51845e62b106d245cc96c431d8aae42">
<input type="submit" value="Оплатить">
</form>
```

