callbacks.payment

$description
API callback request that is sent when an in-game payment is being processed

$params#uid
User id

$params#transaction_id
Unique payment transaction id

$params#transaction_time
Transaction time in yyyy-mm-dd HH:MM:SS format

$params#product_code
Product code

$params#product_option
Product option code

$params#amount
Amount of currency paid for a product within transaction

$params#currency
Payment currency (if product was payed in OKs this field is not sent)

$params#payment_system
Payment system for RUB payments

$params#extra_attributes
JSON with additional transaction information which game send via [FAPI.UI.showPayment](/n/dev/sdk/js/ui.showPayment) method

$params#trial_days
Trial period of game subscription payment

$params#card_promo


$additional
Additional information about in-game payments can be found on [in-game payment example](/en/dev/examples/payment) page.

* Callback is sent up to 3 times. Retry period - 5 seconds. Request is sent again if game server does not respond correctly. If after 3 retries game server still does not respond, transaction is cancelled.
* Only HTTP GET request can be send.
* Only XML-type response is supported.
* Content-type should be "application/xml".
* In case of an error it's code should be passed in "Invocation-error" HTTP-header.
* Developer must validate product's price and code. Not following this recommendation can result in fake in-game purchases.
* Developer must validate [request signature](/en/dev/methods/).


Request are to come only from following addresses:

* 217.20.145.192/28
* 217.20.151.160/28
* 217.20.153.48/28

**Error codes**

|          Name          |Code|Description                                              |
|------------------------|----|---------------------------------------------------------|
|        UNKNOWN         |  1 |Unknown error                                            |
|         SERVICE        |  2 |Service is temporary unavailable                         |
|CALLBACK_INVALID_PAYMENT|1001|Payment is invalid and can't be processed                |
|         SYSTEM         |9999|Critical system error                                    |
|    PARAM_SIGNATURE     |104 |Invalid request signature                                |

**Response examples**

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