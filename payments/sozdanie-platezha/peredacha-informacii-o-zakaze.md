# Передача информации о заказе

В некоторых случаях на форму оплаты необходимо отправить данные о составе заказа, как то - название товара/услуги, количество и стоимость. Для этого необходимо включить в запрос следующие данные:

```text
<input type="hidden" name="receipt[items][0][name]" value="Пример услуги">
<input type="hidden" name="receipt[items][0][count]" value="1">
<input type="hidden" name="receipt[items][0][price]" value="2">

<input type="hidden" name="receipt[items][1][name]" value="Пример услуги 2">
<input type="hidden" name="receipt[items][1][count]" value="4">
<input type="hidden" name="receipt[items][1][price]" value="2">

<!-- общая сумма оплаты должна равняться сумме всех товаров! -->
<input type="hidden" name="amount" value="10">
```

**Внимание!** Данную форму необходимо отправлять на наш платежный урл методом **POST**

