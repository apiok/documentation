callbacks.payment

$description
Обратная связь, вызываемая API для уведомления удаленного сервера приложений о завершении транзакции

$params#uid
Идентификатор пользователя

$params#transaction_id
Уникальный идентификатор транзакции

$params#transaction_time
Время транзакции в формате yyyy-mm-dd HH:MM:SS

$params#product_code
Код продукта

$params#product_option
Код выбранного варианта продукта

$params#amount
Общая сумма в виртуальной валюте портала

$params#currency
Валюта платежа (за исключением платежей в «ok»)

$params#payment_system
Система оплаты в случае прямых платежей в валюте RUR

$params#extra_attributes
JSON-кодированные пары ключей/значений, содержащие дополнительные параметры транзакции, которые передает приложение в методе [FAPI.UI.showPayment](/dev/sdk/js/ui.showPayment).

$params#trial_days
Пробный период в днях купленной игровой подписки

$params#card_promo


$additional
См. также [пример проведения платежа](/dev/examples/payment) в HTML-приложении с серверной частью на PHP.

* Обратная связь вызывается 3 раза до получения успешного ответа HTTP. Каждая попытка имеет задержку 5 секунд. Если сервер не отвечает, транзакция будет отменена, а виртуальные деньги возвращены пользователю.
* Работает только через HTTP GET;
* Поддерживает только ответы XML (см. примеры таких ответов ниже);
* Тип содержимого должен быть "application/xml";
* В случае ошибки HTTP-заголовок "Invocation-error" должен содержать код ошибки;
* Разработчик обязан проверять соответствие товара и его цены, передаваемых в параметрах product_code и amount. В противном случае злоумышленник сможет совершать любые покупки в игре за минимальную стоимость;
* Разработчик должен проверять [значение подписи sig](/dev/methods/) из запроса.

Список адресов, с которых будет вызываться метод:

* 217.20.145.192/28
* 217.20.151.160/28
* 217.20.153.48/28

**Коды ошибок**

|          Имя           |Код |Описание|
|------------------------|----|--------|
|        UNKNOWN         |  1 |Неизвестная ошибка
|         SERVICE        |  2 |Сервис временно недоступен|
|CALLBACK_INVALID_PAYMENT|1001|Платеж неверный и не может быть обработан|
|         SYSTEM         |9999|Критический системный сбой, который невозможно устранить|
|    PARAM_SIGNATURE     |104 |Неверная подпись|

**Варианты ответа**

{% highlight xml %}
<?xml version="1.0" encoding="UTF-8"?>
<callbacks_payment_response xmlns="http://api.forticom.com/1.0/">
    true
</callbacks_payment_response>
{% endhighlight %}

{% highlight xml %}
<?xml version="1.0" encoding="UTF-8"?>
<ns2:error_response xmlns:ns2='http://api.forticom.com/1.0/'>
    <error_code>1001</error_code>
    <error_msg>CALLBACK_INVALID_PAYMENT : Payment is invalid and can not be processed</error_msg>
</ns2:error_response>
{% endhighlight %}