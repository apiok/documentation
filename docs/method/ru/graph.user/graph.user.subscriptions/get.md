graph.user.subscriptions

$description
Получение списка Webhook'ов подписки

$additional
**Пример запроса**

{% format_code https://api.ok.ru/graph/me/subscriptions?access_token=tkn18YdUJZe:CQABPOJKAKEKEKEKE %}

**Ответ**

{% highlight json %}
{
  "subscriptions": [                                    /* Список URL'ов, на которые приходят сообщения от API */
    {
      "time": 1498577751487,                            /* Время, в которое была совершена подписка */
      "url": "https://sample.com/webhook.php"           /* URL webhook'а */
    }
  ]
}
{% endhighlight %}