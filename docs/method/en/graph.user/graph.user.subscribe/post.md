graph.user.subscribe

$description
Subscribe to be notified about new chat events

$payload
{% highlight json %}
{
  "url": String  /* http: or https: URL, where messages about new chat events will be sent */
}
{% endhighlight %}

$additional
{% format_code Content-Type: application/json;charset=utf-8 header should be specified for all Graph API POST requests %}

**Processing API requests**

Messages about all new chat events will be sent to every Webhook registered by this method.

Messages about this events are sent to Webhook:

* chat state updates (new icon or title);
* new chat messages (except messages by Webhook / access_token owner);
* new chat participant's actions (user was added or removed from chat, user has left chat)

If a message contains image, video or any other attachment, Webhook message will have it too.

Requests can come from following IP-addresses:

* 217.20.145.192/28
* 217.20.151.160/28
* 217.20.153.48/28

{% format_code https://api.ok.ru/graph/me/subscribe?access_token=tkn18YdUJZe:CQABPOJKAKEKEKEKE %}

**POST-payload example**

{% highlight json %}
{
  "url": "http://sample.com/webhook.php"        /* http: or https: URL, where messages about new chat events will be sent */
}
{% endhighlight %}

Webhook messages are sent as a HTTP-POST request in a JSON format.

On each such request Webhook should give a 200 HTTP status code response within 5 seconds.
If it fails to respond with a correct answer, API will try to send a message again.
If Webhook did not respond in 8 hours, it could be removed from subscriptions list.

**Response**

{% highlight json %}
{
  "success": true       /* Indicates if a subscription event was successfully executed */
}
{% endhighlight %}

**Webhook message examples**

Webhook messages should be same as messages that are being sent by method me/message/post

Plain text message example:

{% highlight json %}
{
  "sender": {
    "user_id": "user:123456789012"
  },
  "recipient": {
    "chat_id": "chat:C3ecb9d02a600"
  },
  "message": {
    "text": "text",
    "seq": 98211023614189660,
    "mid": "mid:C3ecb9d02a600.15cea67d78d2059"
  },
  "timestamp": 1498581292941
}
{% endhighlight %}

Message with an attachment example:

{% highlight json %}
{
  "sender": {
    "user_id": "user:123456789012"
  },
  "recipient": {
    "chat_id": "chat:C3ecb9d02a600"
  },
  "message": {
    "text": "https://ya.ru/",
    "seq": 98211018056672380,
    "attachments": [
      {
        "type": "SHARE",
        "payload": {
          "url": "https://ya.ru/"
        }
      }
    ],
    "mid": "mid:C3ecb9d02a600.15cea668c4c2481"
  },
  "timestamp": 1498581208140
}
{% endhighlight %}