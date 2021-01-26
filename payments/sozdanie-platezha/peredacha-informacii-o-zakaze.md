# Передача информации о заказе

В некоторых случаях на форму оплаты необходимо отправить данные о составе заказа, как то - название товара/услуги, количество и стоимость. Для этого необходимо включить в запрос параметр **receipt**, например:

```php
<form action="https://pay.roskassa.net/form/" method="post">
<input type="hidden" name="shop_id" value="D0F98E7D7742609DC508D86BB7500914">


<!-- Товар 1 -->
<input type="hidden" name="receipt[items][0][name]" value="Пример услуги">
<input type="hidden" name="receipt[items][0][count]" value="1">
<input type="hidden" name="receipt[items][0][price]" value="20">

<!-- Товар 2 -->
<input type="hidden" name="receipt[items][1][name]" value="Пример услуги 2">
<input type="hidden" name="receipt[items][1][count]" value="2">
<input type="hidden" name="receipt[items][1][price]" value="40">


<!-- общая сумма оплаты должна равняться сумме всех товаров! -->
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

**Внимание!** Данную форму необходимо отправлять на наш платежный урл методом **POST**

